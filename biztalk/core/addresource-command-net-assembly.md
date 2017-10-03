---
title: 'Comando AddResource: Ensamblado de .NET | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef6ec298-35fe-4845-9549-685993d2c659
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f20e259611d312429c3bd909a85a3162f1dd64
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command-net-assembly"></a>AddResource (comando): Ensamblado de .NET
Para agregar un ensamblado .NET (que incluye componentes administrados COM o COM +) a una aplicación de BizTalk, use la **AddResource** comando y especifique **System.BizTalk:Assembly** para el parámetro de tipo. Ejecutar este comando agrega el ensamblado a la base de datos de administración de BizTalk. Además, el ensamblado aparece en la consola de administración de BizTalk Server en la carpeta Recursos de la aplicación a la que lo agregó. Además, el ensamblado se enumera cuando se utiliza el [comando ListApp](../core/listapp-command.md).  
  
 Si un ensamblado tiene el mismo nombre completo que un ensamblado ya existente en la aplicación, puede especificar el parámetro Overwrite. El nombre completo consta del nombre, del token de clave pública, de la referencia cultural y de la versión. En este caso, se sobrescribe el ensamblado existente. Para obtener más información acerca de las dependencias, consulte [dependencias e implementación de aplicaciones](../core/dependencies-and-application-deployment.md).  
  
## <a name="usage"></a>Uso  
 **BTSTask AddResource** [**/ApplicationName:***valor*] **/Type:System.BizTalk:Assembly**[**/Overwrite**] **/Source:***valor* [**/Destination:***valor*] [**/Options:GacOnAdd** *&#124;*  **GacOnInstall***&#124;* **GacOnImport**&#124; **Opción RegasmOnInstall**&#124; **RegsvcsOnInstall**] [**/Server:***valor*] [**/Database:***valor*]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|No|Nombre de la aplicación de BizTalk a la que se agrega el ensamblado. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo.|  
|**/ Escriba** (o **/T**, vea la sección Comentarios)|Sí|**System.BizTalk:Assembly** (este valor no distingue entre mayúsculas y minúsculas).|  
|**/ Sobrescribir** (o **/Ov**, vea la sección Comentarios)|No|Opción para actualizar un ensamblado existente. Si no se especifica y ya existe un ensamblado en la aplicación que tiene el mismo nombre completo que el ensamblado que se agrega, se produce un error en la operación AddResource. El nombre completo consta del nombre de ensamblado, de la versión, de la referencia cultural y del token de clave pública. Esta información se muestra en el campo Nombre de la carpeta Recursos de la aplicación dentro de la consola de administración de BizTalk Server.|  
|**/ Origen** (o **/So**, vea la sección Comentarios)|Sí|Ruta de acceso completa al archivo de ensamblado, incluido el nombre de archivo. Si la ruta incluye espacios, los debe encerrar entre comillas dobles (").|  
|**/ Destino** (o **/De**, vea la sección Comentarios)|No|Ruta completa de la ubicación en la que se va a copiar el archivo de ensamblado cuando se instale la aplicación desde el archivo .msi. Si no se proporciona, el archivo de ensamblado no se copia al sistema de archivos local durante instalación. Si la ruta incluye espacios, los debe encerrar entre comillas dobles ("). Si especifica la opción RegasmOnInstall o RegsvcsOnInstall, también debe especificar Destino. **Nota:** puede usar la variable de entorno % BTAD_InstallDir % para especificar la carpeta de instalación de la aplicación. Esto crea una ubicación coherente para los archivos de la aplicación en equipos de destino diferentes. Ejemplo: "% BTAD_InstallDir%\MyAssemblies\Orchestrations.dll"|  
|**/ Opciones de** (o **/Op**, vea la sección Comentarios)|No|-   **GacOnAdd**: instalar el ensamblado a la caché de ensamblados global (GAC) en el equipo local durante la operación AddResource.<br />-   **GacOnInstall**: instale el ensamblado a la GAC cuando se instala la aplicación desde el archivo MSI.<br />-   **GacOnImport**: instale el ensamblado a la GAC cuando se importa el archivo .msi de aplicación.<br />-   **Opción RegasmOnInstall**: agregar un ensamblado COM administrado al registro de Windows cuando se instala la aplicación desde el archivo MSI. Si especifica esta opción, también debe especificar Destino.<br />-   **RegsvcsOnInstall**: agregar un ensamblado COM + administrado al registro de Windows cuando se instala la aplicación desde el archivo MSI. Si especifica esta opción, también debe especificar Destino.<br /><br /> Debe separar varias opciones mediante una coma. No puede haber espacios entre comas y valores.|  
|**/ Servidor** (o **/Se**, vea la sección Comentarios)|No|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|No|Nombre de la base de datos de administración de BizTalk. Si no se proporciona, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **Tipo de BTSTask AddResource /ApplicationName:MyApplication /: System.BizTalk:Assembly / Overwrite /Source:"%BTAD_InstallDir%\Source Assemblies\MyAssembly.dll" /Destination:"%BTAD_InstallDir%\New Assemblies\MyAssembly.dll" /Options:GacOnAdd, Opción RegasmOnInstall /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [AddResource (comando)](../core/addresource-command.md)   
 [Cómo agregar un ensamblado de .NET a una aplicación](../core/how-to-add-a-net-assembly-to-an-application.md)