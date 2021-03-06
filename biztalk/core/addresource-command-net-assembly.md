---
title: 'AddResource (comando): Ensamblado de .NET | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef6ec298-35fe-4845-9549-685993d2c659
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2723eb8cf3cff6e90554507b65a2a02c6f8ed1a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999757"
---
# <a name="addresource-command-net-assembly"></a>AddResource (comando): Ensamblado de .NET
Para agregar un ensamblado .NET (que incluye los componentes administrados COM o COM +) a una aplicación de BizTalk, usa el **AddResource** comando y especifique **BizTalk: Assembly** para el parámetro de tipo. Ejecutar este comando agrega el ensamblado a la base de datos de administración de BizTalk. Además, el ensamblado aparece en la consola de administración de BizTalk Server en la carpeta Recursos de la aplicación a la que lo agregó. Además, el ensamblado se enumera cuando se utiliza el [comando ListApp](../core/listapp-command.md).  
  
 Si un ensamblado tiene el mismo nombre completo que un ensamblado ya existente en la aplicación, puede especificar el parámetro Overwrite. El nombre completo consta del nombre, del token de clave pública, de la referencia cultural y de la versión. En este caso, se sobrescribe el ensamblado existente. Para obtener más información acerca de las dependencias, consulte [dependencias e implementación de aplicación](../core/dependencies-and-application-deployment.md).  
  
## <a name="usage"></a>Uso  
 **BTSTask AddResource** [**/ApplicationName:**<em>valor</em>] **/Type:System.BizTalk:Assembly**[**/Overwrite**] **/Source:**<em>valor</em> [**/Destination:**<em>valor</em>] [**/Options:GacOnAdd** <em>&#124;</em> **GacOnInstall**<em>&#124;</em>**GacOnImport**&#124;**RegasmOnInstall**  &#124; **RegsvcsOnInstall**] [**/Server:**<em>valor</em>] [**/Database:**  <em>valor</em>]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|no|Nombre de la aplicación de BizTalk a la que se agrega el ensamblado. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo.|  
|**/ Escriba** (o **/T**, vea la sección Comentarios)|Sí|**BizTalk: Assembly** (este valor no distingue mayúsculas de minúsculas).|  
|**/ Sobrescribir** (o **/Ov**, vea la sección Comentarios)|no|Opción para actualizar un ensamblado existente. Si no se especifica y ya existe un ensamblado en la aplicación que tiene el mismo nombre completo que el ensamblado que se agrega, se produce un error en la operación AddResource. El nombre completo consta del nombre de ensamblado, de la versión, de la referencia cultural y del token de clave pública. Esta información se muestra en el campo Nombre de la carpeta Recursos de la aplicación dentro de la consola de administración de BizTalk Server.|  
|**/ Origen** (o **/So**, vea la sección Comentarios)|Sí|Ruta de acceso completa del archivo de ensamblado, incluido el nombre de archivo. Si la ruta incluye espacios, los debe encerrar entre comillas dobles (").|  
|**/ Destino** (o **/De**, vea la sección Comentarios)|no|Ruta completa de la ubicación en la que se va a copiar el archivo de ensamblado cuando se instale la aplicación desde el archivo .msi. Si no se proporciona, el archivo de ensamblado no se copia al sistema de archivos local durante instalación. Si la ruta incluye espacios, los debe encerrar entre comillas dobles ("). Si especifica la opción RegasmOnInstall o RegsvcsOnInstall, también debe especificar Destino. **Nota:** puede usar la variable de entorno % BTAD_InstallDir % para especificar la carpeta de instalación de la aplicación. Esto crea una ubicación coherente para los archivos de la aplicación en equipos de destino diferentes. Ejemplo: "% BTAD_InstallDir%\MyAssemblies\Orchestrations.dll"|  
|**/ Las opciones** (o **/op.**, vea la sección Comentarios)|no|-   **GacOnAdd**: instalar el ensamblado a la caché de ensamblados global (GAC) en el equipo local durante la operación AddResource.<br />-   **GacOnInstall**: instalar el ensamblado en la GAC cuando se instala la aplicación desde el archivo MSI.<br />-   **GacOnImport**: instalar el ensamblado en la GAC cuando se importa el archivo .msi de aplicación.<br />-   **RegasmOnInstall**: agregar un ensamblado COM administrado al registro de Windows cuando se instala la aplicación desde el archivo MSI. Si especifica esta opción, también debe especificar Destino.<br />-   **RegsvcsOnInstall**: agregar un ensamblado COM + administrado al registro de Windows cuando se instala la aplicación desde el archivo MSI. Si especifica esta opción, también debe especificar Destino.<br /><br /> Debe separar varias opciones mediante una coma. No puede haber espacios entre comas y valores.|  
|**/ Servidor** (o **/Se**, vea la sección Comentarios)|no|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|no|Nombre de la base de datos de administración de BizTalk. Si no se proporciona, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **Tipo de BTSTask AddResource /ApplicationName:MyApplication /: BizTalk: Assembly / Overwrite /Source:"%BTAD_InstallDir%\Source Assemblies\MyAssembly.dll" /Destination:"%BTAD_InstallDir%\New Assemblies\MyAssembly.dll" /Options:GacOnAdd, RegasmOnInstall /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Notas  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [AddResource (comando)](../core/addresource-command.md)   
 [Cómo agregar un ensamblado .NET a una aplicación](../core/how-to-add-a-net-assembly-to-an-application.md)