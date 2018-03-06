---
title: "Agregar un archivo de enlace a una aplicación | Documentos de Microsoft"
description: "Agregar un archivo de enlace mediante administración de BizTalk Server o utilizar el símbolo del sistema en BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1543ee5f-9ae4-4683-b6fe-ee84028c381d
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6d2a999be4a12860616bc92f3086b37dbd265f
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="add-a-binding-file-to-an-application"></a>Agregar un archivo de enlace a una aplicación

## <a name="overview"></a>Información general
Usar la consola de administración de BizTalk Server o la línea de comandos para agregar un archivo de enlace a una aplicación de BizTalk. Puede hacerlo para facilitar la implementación de aplicación o ensamblado, tal como se describe en [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
 Puede exportar enlaces a un archivo .xml desde una aplicación de BizTalk para un ensamblado, la aplicación o el grupo, como se describe en [exportar enlaces](../core/exporting-bindings6.md)y, a continuación, use uno de los procedimientos de este tema para agregar el archivo de enlace a una aplicación.  
  
 Al hacerlo, el archivo de enlace se agrega a la base de datos de administración de BizTalk y se muestra en la consola de administración de BizTalk Server, en la carpeta Recursos de la aplicación. A diferencia de lo que ocurre al importar un archivo de enlace, agregar un archivo de enlace no aplica inmediatamente los enlaces que contiene. En cambio, los enlaces se aplican cuando la aplicación se importa a otro grupo de BizTalk.  
  
> [!IMPORTANT]
>  Por motivos de seguridad, cuando se exportan enlaces, BizTalk Server quita las contraseñas de los enlaces del archivo. Después de importar los enlaces, deberá volver a configurar las contraseñas para que funcionen los puertos de envío y las ubicaciones de recepción. Configure las contraseñas en el cuadro de diálogo Propiedades de transporte de la consola de administración de BizTalk Server para el puerto de envío o la ubicación de recepción. Vea [crear un puerto de envío](../core/how-to-create-a-send-port2.md) o [crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
> [!NOTE]
>  Cuando se usa un archivo de enlace, debe comprobar que los artefactos se han enlazado al host correcto y que el nivel de confianza sea la adecuada.  
  
 Cuando se agrega un archivo de enlace a una aplicación, puede especificar un valor para el entorno de implementación de destino mediante una cadena que representa el entorno (de prueba, o producción, por ejemplo). Puede utilizar cualquier cadena para este valor. Posteriormente, cuando importe la aplicación, podrá seleccionar qué archivo de enlace desea aplicar proporcionando el valor especificado para su entorno de destino. Al hacerlo, los enlaces se aplican desde el archivo de enlace: Los enlaces existentes en la aplicación que tengan el mismo nombre que los enlaces del archivo se sobrescriben automáticamente.  
  
 Cuando se importa una aplicación, los enlaces se aplican en el orden siguiente. A medida que se aplican los enlaces durante el proceso de importación, los enlaces que ya se han aplicado se sobrescriben con enlaces nuevos que tienen el mismo nombre. Es decir, surtirá efecto el último enlace de un nombre concreto que se aplica.  
  
1.  Los enlaces de la aplicación generados por BizTalk Server que no se agregaron explícitamente a la aplicación mediante un archivo de enlace, pero que el usuario seleccionó explícitamente para exportarlos al archivo .msi de la aplicación.  
  
2.  Los archivos de enlace que se han agregado explícitamente y que no tienen especificado un entorno de implementación de destino. Los enlaces de este conjunto no se aplican en ningún orden específico.  
  
3.  Los enlaces que se ha agregado explícitamente y que tienen un entorno de implementación de destino asociado que coincide con el entorno de implementación seleccionado para la importación de la aplicación. Los enlaces de este conjunto no se aplican en ningún orden específico.  
  
 Para obtener más información sobre la importación de las aplicaciones y aplicar los enlaces, vea [importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro del grupo Administradores de BizTalk Server. [Permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md) proporcionan más detalles.
  
## <a name="add-a-binding-file-using-biztalk-administration"></a>Agrega un archivo de enlace mediante administración de BizTalk  
  
1.  Abra **administración de BizTalk Server** (en el menú Inicio).
  
2.  Expanda Administración de BizTalk Server, expanda el grupo de BizTalk, expanda aplicaciones y haga clic en la aplicación a la que desea agregar un archivo de enlace.  
  
3.  Seleccione **agregar**y, a continuación, haga clic en **recursos**.  
  
4.  Haga clic en **agregar**, seleccione el archivo para agregar y, a continuación, haga clic en **abiertos**.  
  
5.  Para sobrescribir un archivo de enlace existente en la aplicación con el mismo nombre de archivo, seleccione la **sobrescribir todos** casilla de verificación. Si existe otro archivo con el mismo nombre y no activa esta casilla, se producirá un error al agregar.  
  
6.  En el **tipo de archivo** lista desplegable, seleccione **BizTalk: biztalkbinding**.  
  
7.  En **entorno de destino**, escriba una cadena que represente el entorno de implementación de destino donde desea que los enlaces de este archivo se aplican, como prueba, y haga clic en **Aceptar**.  
  
    > [!IMPORTANT]
    >  Si deja en blanco este campo, los enlaces de este archivo se aplicarán siempre al importar la aplicación.  
  
     Se agrega el archivo de enlace y se muestra en la carpeta Recursos de la aplicación.  
  
## <a name="add-a-binding-file-using-the-command-line"></a>Agrega un archivo de enlace mediante la línea de comandos  
  
1.  Abra un símbolo del sistema (**iniciar** menú > escriba `cmd` > seleccione **símbolo**).  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask AddResource** [**/ApplicationName:"***value***"**] **/Type:System.BizTalk:BizTalkBinding** [**/Overwrite**] **/Source:***value***/Property:TargetEnvironment="***value***"** [**/Server:***value*] [**/Database:***value*]  
  
     Ejemplo:  
  
     **BTSTask AddResource /ApplicationName:"My Application" /Type:System.BizTalk:BizTalkBinding  /Source:"C:\Binding Files\MyBinding.xml" /Property:TargetEnvironment="Production" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |Parámetro|Value|  
    |---------------|-----------|  
    |**/ApplicationName**|Nombre de la aplicación de BizTalk a la que se agrega el archivo de enlace. Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
    |**/Type**|**BizTalk: biztalkbinding** (este valor no distingue entre mayúsculas y minúsculas).|  
    |**/Overwrite**|Opción para actualizar un archivo de enlace existente. Si no especificado y enlace el archivo ya existe en la aplicación que tiene el mismo nombre de archivo que el archivo que se agrega, se produce un error en la operación AddResource.|  
    |**Código fuente**|Ruta completa del archivo de enlace, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
    |**/Property:TargetEnvironment=**|Cadena que especifica el entorno de implementación de destino. Puede utilizar cualquier cadena, por ejemplo Producción. Ejemplo: **/Property:TargetEnvironment = "Producción"**<br /><br /> Si no se especifica, un valor de \<predeterminado\> se aplica automáticamente. El valor distingue mayúsculas de minúsculas. Si el valor incluye espacios, lo debe encerrar entre comillas dobles ("). La longitud máxima del valor del entorno es 128 caracteres.|  
    |**/Server**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/Database**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar ensamblados. NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [El comando AddResource: Enlace de BizTalk](../core/addresource-command-biztalk-binding.md)   
 [Creación y modificación de aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)