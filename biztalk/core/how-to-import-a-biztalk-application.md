---
title: Cómo importar una aplicación de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, planning
- planning, importing
- importing, applications
- applications, planning
- planning, deploying
- applications, importing
- importing, planning
ms.assetid: 51169f35-d572-4612-9104-a59908e24874
caps.latest.revision: 70
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65a2e29be82cb55b0c8509eb3adb346f48d5b794
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010373"
---
# <a name="how-to-import-a-biztalk-application"></a>Cómo importar una aplicación de BizTalk
En este tema se describe cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o la línea de comandos para importar una aplicación de BizTalk en un grupo de BizTalk. La importación de una aplicación de BizTalk registra los artefactos en la base de datos de administración de BizTalk y escribe los datos de aquéllos en las bases de datos de BizTalk apropiadas. Para obtener más información, consulte [¿qué ocurre cuando artefactos se importarán](../core/what-happens-when-artifacts-are-imported.md). Cuando se instala una aplicación, ésta no se instala. Antes de poder ejecutar una aplicación que incluya artefactos basados en archivos, es preciso instalarla.  
  
 Al usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para importar una aplicación, la ubicación desde la que se inicia el Asistente para importación de MSI determina la posibilidad o no de crear una nueva aplicación a la vez que se efectúa la importación de los artefactos. Si inicia el Asistente haciendo clic con el botón secundario en el grupo de BizTalk, tendrá que proporcionar un nombre de aplicación. Si una aplicación del grupo de BizTalk tiene el nombre especificado, los artefactos del archivo se importan en esta aplicación; de lo contrario, se creará una nueva aplicación con el nombre especificado en la que se importan los artefactos. Si se inicia el Asistente haciendo clic con el botón secundario en una aplicación, no será posible especificar un nombre de aplicación y los artefactos se importarán en la aplicación actual.  
  
 Al utilizar la herramienta de línea de comandos BTSTask para importar un archivo .msi, la especificación de un nombre de aplicación es opcional. Si no se proporciona un nombre, sus artefactos se importarán en la aplicación predeterminada.  
  
 Tras importar los artefactos, es posible verlos en la carpeta adecuada de la carpeta de la aplicación en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. También puede ver una lista de artefactos en la aplicación mediante BTSTask, tal y como se describe en [comando ListApp](../core/listapp-command.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para importar una aplicación de BizTalk, es preciso haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para instalar una aplicación de BizTalk, también se debe contar, como mínimo, con permisos de escritura en el sistema de archivos local. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="considerations-for-importing-applications"></a>Consideraciones para importar aplicaciones  
 Al importar una aplicación, es preciso tener en cuenta lo siguiente:  
  
-   **Importación de aplicaciones desde versiones anteriores de BizTalk Server**. Si está importando aplicaciones de BizTalk Server 2006 R2 o BizTalk Server 2009 y las aplicaciones contienen datos de entidades EDI/AS2, la importación de la aplicación puede producir porque el modelo de administración de socios comerciales ha cambiado considerablemente en BizTalk Server. Debe utilizar en su lugar la Herramienta de migración de entidades para migrar los datos de entidades de versiones anteriores de BizTalk Server. Para obtener más información acerca de la herramienta, consulte [migrar artefactos de EDI desde una versión anterior de BizTalk Server](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c).  
  
-   **Los enlaces importados siempre sobrescriben los enlaces existentes.** Al importar un archivo .msi que contenga enlaces en una aplicación existente, los enlaces importados sobrescribirán los existentes que tengan el mismo nombre. Esto ocurre aun si no se ha seleccionado la opción de sobrescritura de los artefactos existentes al importar el archivo .msi. Si no desea que los enlaces de la aplicación que se está exportando sobrescriba los enlaces de la aplicación en la que se está importando el archivo .msi, no seleccione el archivo de enlace como un recurso que es preciso exportar durante la exportación. Para obtener más información, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
     A medida que se aplican los enlaces durante el proceso de importación, los enlaces que ya se han aplicado se sobrescriben con enlaces nuevos que tienen el mismo nombre. Es decir, surtirá efecto el último enlace de un nombre concreto que se aplica. Cuando importa una aplicación, los enlaces se aplican en el orden siguiente:  
  
    1.  Los enlaces de la aplicación que genera [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que no se agregaron explícitamente a la aplicación mediante un archivo de enlace, pero que el usuario seleccionó explícitamente para exportarlos al archivo .msi de la aplicación.  
  
    2.  Los archivos de enlace que se han agregado explícitamente y que no tienen especificado un entorno de implementación de destino. Los enlaces de este conjunto no se aplican en ningún orden específico.  
  
    3.  Los enlaces que se ha agregado explícitamente y que tienen un entorno de implementación de destino asociado que coincide con el entorno de implementación seleccionado para la importación de la aplicación. Los enlaces de este conjunto no se aplican en ningún orden específico.  
  
-   **El host debe existir en el grupo.** En el grupo de BizTalk, debe existir un host correspondiente al especificado en los enlaces de la aplicación que contiene el archivo.msi; de lo contrario, se producirán errores en la operación de importación. Además, es necesario que el nivel de confianza del host coincida.  
  
-   **Debe agregar una referencia a otra aplicación.** Si la aplicación que se importa depende de un artefacto de otra aplicación, es posible que se deba agregar una referencia a esta aplicación. Es preciso que tanto la aplicación como el artefacto requerido existan en el grupo. El Asistente para importación proporciona esta opción. Si usa el comando ImportApp de BTSTask, sin embargo, debe agregar la referencia a la aplicación después de la importación, como se describe en [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md). Para obtener información general, vea [dependencias e implementación de aplicaciones](../core/dependencies-and-application-deployment.md). El Asistente para importación hace coincidir las referencias con las aplicaciones existentes en el grupo y proporciona la opción de agregar una nueva referencia o cambiar una referencia existente. Como paso adicional, debería comprobarse que la aplicación a la que se ha hecho referencia contiene el artefacto requerido.  
  
-   **Si se agota el tiempo de espera de una operación de importación, divida la aplicación en archivos .msi adicionales.** Una operación de importación agotará el tiempo de espera si supera 3600 segundos de duración. Si está intentando importar un archivo .msi y la operación agota el tiempo de espera, debería dividir el contenido de la aplicación en más de un archivo .msi exportando de nuevo la aplicación y seleccionando un subconjunto de artefactos para exportarlos. Para obtener más información, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
> [!IMPORTANT]
>  Por motivos de seguridad, las contraseñas se quitan de los enlaces de aplicación durante la exportación de la aplicación. No obstante, no se quitan de ningún archivo de enlace que se haya agregado a la aplicación. Después de importar la aplicación, se deberá volver a configurar las contraseñas para que funcione la aplicación. Esto puede llevarse a cabo editando el archivo de enlace o mediante la consola de administración. Para obtener más información acerca de cómo editar un archivo de enlace, vea [personalizar archivos de enlace](../core/customizing-binding-files.md). Para obtener más información acerca de cómo configurar la seguridad de adaptadores, vea [usando adaptadores](../core/using-adapters.md).  
  
> [!NOTE]
>  Si se producen errores en una importación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deshace todas las operaciones de importación, excepto las acciones llevadas a cabo mediante scripts personalizados.  
  
> [!NOTE]
>  Si crea un filtro para un puerto de envío en una aplicación que utilice un esquema de propiedades en otra aplicación y si, a continuación, importa la primera aplicación en un nuevo grupo de BizTalk, no recibirá ninguna advertencia de la falta del esquema, y el filtrado no se efectuará una vez instalada e iniciada la aplicación. Puede corregir el problema importando la aplicación que contiene el esquema antes de instalar la aplicación que no contiene el esquema.  
  
## <a name="to-import-a-biztalk-application"></a>Para importar una aplicación de BizTalk  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Utilizar la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de la consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y el grupo de BizTalk. A continuación, efectúe una de las acciones siguientes:  
  
    -   Para importar la aplicación y los artefactos contenidos en el archivo .msi en el grupo de BizTalk, haga clic en **aplicaciones**, seleccione **importar**y, a continuación, haga clic en **archivo MSI**.  
  
    -   Para importar los artefactos contenidos en el archivo .msi en una aplicación existente, expanda **aplicaciones**, haga clic en la aplicación, seleccione **importar**y, a continuación, haga clic en **archivo MSI**.  
  
3.  En la página Asistente para la página del Asistente para importación de MSI, en **archivo MSI para importar**, escriba la ruta de acceso del archivo .msi y, a continuación, haga clic en **siguiente**. Si es necesario, también puede examinar el archivo .msi haciendo clic en el **...** .  
  
4.  En la página Configuración de la aplicación, en la **nombre de la aplicación** lista de lista desplegable, seleccione el nombre de la aplicación, si está disponible. La lista se encuentra disponible en el caso de importar la aplicación en el grupo de BizTalk.  
  
    > [!NOTE]
    >  Esta lista incluye los nombres de todas las aplicaciones que se encuentran actualmente en el grupo de BizTalk, además de la aplicación desde la que se exporta el archivo .msi. Si se selecciona el nombre de esta última aplicación y ésta no existe en el grupo de BizTalk, el Asistente para importación creará una nueva aplicación. Si se selecciona una aplicación ya existente en el grupo, el Asistente para importación importa los artefactos del archivo .msi en la aplicación existente.  
  
5.  En **aplicaciones disponibles para agregar referencias a**, seleccione las aplicaciones que se va a agregar referencias, si los hay y, a continuación, haga clic en **siguiente**.  
  
6.  Si va a importar el archivo .msi en una aplicación existente y desea sobrescribir artefactos de la aplicación existente, seleccione **sobrescribir recursos**.  
  
    > [!NOTE]
    >  Si no selecciona esta opción y el archivo .msi contiene un artefacto ya existente en la aplicación, se producirán errores en la operación de importación y ésta se deshará. Ciertos tipos de artefactos de la aplicación o del grupo de BizTalk deben ser únicos. Si se agrega un artefacto ya existente en el grupo de BizTalk, pero no en la aplicación actual, la operación de importación no se llevará a cabo correctamente, aun si se especifica la opción de sobrescritura. Para obtener más información acerca de qué artefactos deben ser únicos y de qué formas deben ser únicos, vea [artefactos que deben ser únicos en una aplicación o un grupo de](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).  
  
7.  En la página de configuración del entorno de destino de aplicación, en la **entorno de ensayo de destino** la lista desplegable, seleccione el entorno de destino para esta aplicación y haga clic en **siguiente**. Esta lista contiene todos los entornos especificados para cualquiera de los archivos de enlace agregados a esta aplicación. Seleccione \<predeterminado\> si desea aplicar todos los enlaces de la aplicación, excepto los que tienen un entorno de destino especificado. Si el archivo .msi no contiene un archivo de enlace que desea aplicar de forma explícita, puede dejar \<predeterminado\> seleccionado.  
  
    > [!NOTE]
    >  El entorno de destino para los enlaces se especifica al agregar un archivo de enlace a una aplicación. Para obtener información general, vea [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md). Para obtener instrucciones sobre cómo agregar archivos de enlace, consulte [cómo agregar un archivo de enlace a una aplicación](../core/how-to-add-a-binding-file-to-an-application2.md).  
  
8.  En la página Importar resumen, confirme que la información de resumen es correcta y, a continuación, haga clic en **importación**.  
  
9. En la página importación se realizó correctamente, si desea instalar la aplicación en el equipo local, seleccione la **ejecutar el Asistente para instalación de aplicaciones para instalar la aplicación en el equipo local** casilla de verificación.  
  
    > [!NOTE]
    >  A menos que sea necesario ejecutar la aplicación tal como está configurada actualmente en el equipo local, no será preciso efectuar su instalación. No obstante, si la aplicación incluye artefactos basados en archivos, se deberá instalar la aplicación en todos los equipos en los que se ejecutará antes de que pueda empezar a funcionar, ya que cuando se importa una aplicación, ésta solo se agrega a la base de datos de administración de BizTalk.  
  
10. Haga clic en **Finalizar**.  
  
> [!NOTE]
>  Si la instalación no se lleva a cabo correctamente porque, por ejemplo, no se dispone de permiso de escritura en el sistema de archivos local, se procederá a deshacer la instalación, pero no la operación de importación.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **ImportApp /Package de BTSTask:** *valor* [**/Environment:***valor*] [**/ApplicationName:**  *valor*] [**/Overwrite**] [**/Server:***valor*] [**/Database:***valor*]  
  
     Ejemplo:  
  
     **/Package ImportApp de BTSTask: "C:\MSI msi\miaplicación. msi" /Environment:Test /ApplicationName:MyApplication / Overwrite**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ Paquete**|Ruta completa del archivo .msi. Si la ruta de acceso incluye espacios, debe encerrarlo entre comillas (").|  
    |**/ Entorno**|El entorno de implementación de destino del archivo de enlace que se va a aplicar, como Prueba. Este es el valor que se especificó para el entorno de implementación de destino cuando se agregó a la aplicación el archivo de enlace.|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk a la que se importan los artefactos del archivo .msi. Si no se especifica, se utiliza el nombre de aplicación especificado al exportar el archivo .msi. Si la aplicación especificada no existe, se creará. Los nombres de aplicación que incluyen espacios deben flanquearse con comillas dobles (").|  
    |**/ Sobrescribir**|Opción para sobrescribir artefactos en la aplicación con artefactos del archivo .msi que tienen el mismo identificador local único (LUID). Si no se especifica esta opción y si hay uno o más artefactos en la aplicación que tienen el mismo LUID que los artefactos del archivo .msi, se produce un error en la importación. Puede ver los LUID de los artefactos de una aplicación mediante el uso de la [comando ListApp](../core/listapp-command.md).|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Importación de directivas, los enlaces y las aplicaciones de BizTalk](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [ImportApp (comando)](../core/importapp-command.md)