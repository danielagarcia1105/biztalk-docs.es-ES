---
title: "Cómo importar una directiva | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, requirements
- importing, policies
- policies, importing
- managing [policies], importing
ms.assetid: 92f6ef18-279f-416d-b13e-8b9642539d27
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bae0b72eb323e75a8ecf9563b4fa0e0bc1b725d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-import-a-policy"></a>Cómo importar una directiva
En este tema se describe cómo usar la consola de administración de BizTalk Server para importar una directiva en un grupo de BizTalk o la herramienta de la línea de comandos BTSTask para importar una directiva en una aplicación de BizTalk.  
  
 Puede crear una directiva mediante el Compositor de reglas de negocios, como se describe en [crear reglas de negocios mediante el Compositor de reglas de negocios](../core/creating-business-rules-using-the-business-rule-composer.md)y, a continuación, importarla directamente, o puede exportar una directiva de otro grupo de BizTalk, tal y como se describe en [Cómo exportar una directiva](../core/how-to-export-a-policy.md) y, a continuación, importarlo.  
  
 Al importar una directiva, se registra en la base de datos del motor de reglas del grupo de BizTalk. Una vez importada la directiva, puede verla en la consola de administración de BizTalk Server. Si utiliza la consola de administración de BizTalk Server para importar una directiva, se mostrará en la \<todos los artefactos > nodo para el grupo de BizTalk. A continuación, puede publicarlo para que esté disponible para agregarlo a una aplicación de BizTalk, tal y como se describe en [cómo publicar una directiva](../core/how-to-publish-a-policy.md). Si usa la herramienta de la línea de comandos BTSTask para importar una directiva, ésta se publicará de forma automática y se mostrará en la carpeta Directivas de la aplicación en la que la importó.  
  
 Al importar una directiva, tenga en cuenta los siguientes puntos importantes:  
  
-   Incluso si especifica la opción de sobrescritura de una directiva existente con la directiva importada, no podrá importar una directiva que exista ya en la base de datos del motor de reglas del grupo y que se haya implementado. La importación no se llevará a cabo correctamente.  
  
-   Incluso si la directiva se encontraba en un estado implementado al exportarla de otro grupo de BizTalk, estará en un estado no implementado cuando se importe.  
  
-   BTSTask no proporciona un comando específico para la importación de directivas; sin embargo puede usar el comando ExportApp de BTSTask para exportar de forma selectiva únicamente las directivas de la aplicación que desee, sin incluir otros artefactos de la aplicación. A continuación, puede usar el comando ImportApp para importar el archivo .msi a una aplicación de un grupo de BizTalk diferente. Éste es el enfoque que se describe en este tema. Al hacerlo, la directiva se importa y se publica de forma automática en el grupo de BizTalk y se agrega a la aplicación especificada.  
  
 Para obtener más información sobre cómo trabajar con las directivas, consulte [administrar directivas](../core/managing-policies.md). Para ver recomendaciones sobre cómo agregar las directivas a las aplicaciones, consulte [prácticas recomendadas para implementar una aplicación de BizTalk](../core/best-practices-for-deploying-a-biztalk-application.md).  
  
> [!NOTE]
>  Puede crear directivas y, a continuación, importarlos en la base de datos de motor de reglas para el grupo mediante el Asistente para la implementación del motor de reglas, como se describe en el programador de soluciones [cómo implementar y anular la implementación de directivas y vocabularios](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:  
  
-   Es preciso haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
-   El motor de reglas de negocios debe estar instalado. Para obtener más información, consulte [Introducción a la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).  
  
-   Si desea usar la consola de administración de BizTalk Server para importar una directiva, debe tener disponible un archivo .xml que contenga la directiva que desea importar. Puede generar este archivo .xml si exporta una directiva de otro grupo de BizTalk o aplicación, como se describe en [cómo exportar una directiva](../core/how-to-export-a-policy.md), o mediante el Compositor de reglas de negocios, como se describe en [cómo importar y exportar Directivas y vocabularios](../core/how-to-import-and-export-policies-and-vocabularies.md).  
  
-   Si desea usar BTSTask para importar una directiva, debe tener un archivo .msi que contenga la directiva que desea importar. Para obtener instrucciones, consulte [cómo exportar una directiva](../core/how-to-export-a-policy.md).  
  
## <a name="to-import-a-policy"></a>Para importar una directiva  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk en el que desea importar la directiva, expanda **aplicaciones**y, a continuación, expanda  **\<todos los artefactos >**.  
  
3.  Haga clic en **directivas**y, a continuación, haga clic en **importación**.  
  
4.  Busque el archivo .xml que contiene la directiva y haga clic en **abiertos**.  
  
     La directiva se importa en el grupo y se muestra en el **directivas** carpeta de  **\<todos los artefactos >**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **ImportApp /Package de BTSTask:** *valor* [**/ApplicationName:***valor*] [**/Overwrite**] [ **/ Server:***valor*] [**/Database:***valor*]  
  
     Ejemplo:  
  
     **/Package ImportApp de BTSTask: "C:\MSI msi\miaplicación. msi" /Environment:Test /ApplicationName:MyApplication / Overwrite**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ Paquete**|Ruta completa del archivo .msi que contenga la directiva que se va a importar. Si la ruta de acceso incluye espacios, debe encerrarlo entre comillas (").|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk en la que se importa la directiva. Si no se especifica, se utiliza el nombre de aplicación especificado al exportar el archivo .msi. Si la aplicación especificada no existe, se creará. Los nombres de aplicación que incluyen espacios deben flanquearse con comillas dobles (").|  
    |**/ Sobrescribir**|Opción para sobrescribir directivas en la aplicación con artefactos del archivo .msi que tienen el mismo nombre y número de versión. Si no se especifica esta opción y hay una o varias directivas en la aplicación que tienen el mismo nombre y número de versión que las directivas del archivo .msi, se produce un error en la importación. Puede ver el nombre y número de versión de las directivas en una aplicación mediante la [comando ListApp](../core/listapp-command.md).|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
## <a name="see-also"></a>Vea también  
 [Importación de directivas, los enlaces y las aplicaciones de BizTalk](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [Exportar aplicaciones de BizTalk, los enlaces y directivas](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [Administración de directivas](../core/managing-policies.md)