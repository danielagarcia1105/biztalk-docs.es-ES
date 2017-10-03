---
title: "Cómo agregar un archivo de enlace a un Application2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], binding files
- applications, binding files
- binding files, applications
ms.assetid: 1543ee5f-9ae4-4683-b6fe-ee84028c381d
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4e569352c5813272b483cc69b8c93a7f1b84d40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-binding-file-to-an-application"></a>Cómo agregar un archivo de enlace a una aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para agregar un archivo de enlace a una aplicación de BizTalk. Puede hacerlo para facilitar la implementación de aplicación o ensamblado, tal como se describe en [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
 Puede exportar enlaces a un archivo .xml desde una aplicación de BizTalk para un ensamblado, la aplicación o el grupo, como se describe en [exportar enlaces](../core/exporting-bindings6.md)y, a continuación, use uno de los procedimientos de este tema para agregar el archivo de enlace a una aplicación.  
  
 Al hacerlo, el archivo de enlace se agrega a la base de datos de administración de BizTalk y se muestra en la consola de administración de BizTalk Server, en la carpeta Recursos de la aplicación. A diferencia de lo que ocurre al importar un archivo de enlace, agregar un archivo de enlace no aplica inmediatamente los enlaces que contiene. En cambio, los enlaces se aplican cuando la aplicación se importa a otro grupo de BizTalk.  
  
> [!IMPORTANT]
>  Por motivos de seguridad, cuando se exportan enlaces, BizTalk Server quita las contraseñas de los enlaces del archivo. Después de importar los enlaces, deberá volver a configurar las contraseñas para que funcionen los puertos de envío y las ubicaciones de recepción. Configure las contraseñas en el cuadro de diálogo Propiedades de transporte de la consola de administración de BizTalk Server para el puerto de envío o la ubicación de recepción. Para obtener instrucciones, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Vea también [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
> [!NOTE]
>  Cuando se usa un archivo de enlace generado en [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)], tenga en cuenta que el nivel de confianza del host no se almacena en el archivo de enlace. Al aplicar los enlaces durante la importación de enlaces o de aplicaciones, los artefactos se enlazan a los hosts únicamente de acuerdo con el nombre del host. Deberá comprobar que los artefactos se hayan enlazado al host correcto y que el nivel de confianza sea el apropiado.  
  
 Cuando se agrega un archivo de enlace a una aplicación, puede especificar un valor para el entorno de implementación de destino mediante una cadena que representa el entorno (de prueba, o producción, por ejemplo). Puede utilizar cualquier cadena para este valor. Posteriormente, cuando importe la aplicación, podrá seleccionar qué archivo de enlace desea aplicar proporcionando el valor especificado para su entorno de destino. Al hacerlo, los enlaces se aplican desde el archivo de enlace: Los enlaces existentes en la aplicación que tengan el mismo nombre que los enlaces del archivo se sobrescriben automáticamente.  
  
 Cuando se importa una aplicación, los enlaces se aplican en el orden siguiente. A medida que se aplican los enlaces durante el proceso de importación, los enlaces que ya se han aplicado se sobrescriben con enlaces nuevos que tienen el mismo nombre. Es decir, surtirá efecto el último enlace de un nombre concreto que se aplica.  
  
1.  Los enlaces de la aplicación generados por BizTalk Server que no se agregaron explícitamente a la aplicación mediante un archivo de enlace, pero que el usuario seleccionó explícitamente para exportarlos al archivo .msi de la aplicación.  
  
2.  Los archivos de enlace que se han agregado explícitamente y que no tienen especificado un entorno de implementación de destino. Los enlaces de este conjunto no se aplican en ningún orden específico.  
  
3.  Los enlaces que se ha agregado explícitamente y que tienen un entorno de implementación de destino asociado que coincide con el entorno de implementación seleccionado para la importación de la aplicación. Los enlaces de este conjunto no se aplican en ningún orden específico.  
  
 Para obtener más información sobre la importación de las aplicaciones y aplicar los enlaces, vea [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-add-a-binding-file-to-an-application"></a>Para agregar un archivo de enlace a una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda Administración de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] y el grupo de BizTalk que contiene la aplicación a la que desea agregar un archivo de enlace.  
  
3.  Expanda Aplicaciones y haga clic con el botón secundario en la aplicación a la que desee agregar el archivo de enlace.  
  
4.  Seleccione **agregar**y, a continuación, haga clic en **recursos**.  
  
5.  Haga clic en **agregar**, seleccione el archivo para agregar y, a continuación, haga clic en **abiertos**.  
  
6.  Para sobrescribir un archivo de enlace existente en la aplicación con el mismo nombre de archivo, seleccione la **sobrescribir todos** casilla de verificación. Si existe otro archivo con el mismo nombre y no activa esta casilla, se producirá un error al agregar.  
  
7.  En el **tipo de archivo** lista desplegable, seleccione **BizTalk: biztalkbinding**.  
  
8.  En **entorno de destino**, escriba una cadena que represente el entorno de implementación de destino donde desea que los enlaces de este archivo se aplican, como prueba, y haga clic en **Aceptar**.  
  
    > [!IMPORTANT]
    >  Si deja en blanco este campo, los enlaces de este archivo se aplicarán siempre al importar la aplicación.  
  
     Se agrega el archivo de enlace y se muestra en la carpeta Recursos de la aplicación.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask AddResource** [**/ApplicationName: "***valor***"**] **/Type:System.BizTalk:BizTalkBinding** [ **/Overwrite**] **/Source:***valor***/Property:TargetEnvironment = "***valor* **"** [**/Server:***valor*] [**/Database:***valor*]  
  
     Ejemplo:  
  
     **/ ApplicationName BTSTask AddResource: "Mi aplicación" /Type:System.BizTalk:BizTalkBinding /Source: /Property:TargetEnvironment "C:\Binding Files\MyBinding.xml" = "Producción" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk a la que se agrega el archivo de enlace. Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
    |**/ Tipo**|**BizTalk: biztalkbinding** (este valor no distingue entre mayúsculas y minúsculas).|  
    |**/ Sobrescribir**|Opción para actualizar un archivo de enlace existente. Si no especificado y enlace el archivo ya existe en la aplicación que tiene el mismo nombre de archivo que el archivo que se agrega, se produce un error en la operación AddResource.|  
    |**Código fuente**|Ruta completa del archivo de enlace, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
    |**/Property:TargetEnvironment =**|Cadena que especifica el entorno de implementación de destino. Puede utilizar cualquier cadena, por ejemplo Producción. Ejemplo: **/Property:TargetEnvironment = "Producción"**<br /><br /> Si no se especifica, un valor de \<predeterminado > se aplica automáticamente. El valor distingue mayúsculas de minúsculas. Si el valor incluye espacios, lo debe encerrar entre comillas dobles ("). La longitud máxima del valor del entorno es 128 caracteres.|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar ensamblados. NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [El comando AddResource: Enlace de BizTalk](../core/addresource-command-biztalk-binding.md)   
 [Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)