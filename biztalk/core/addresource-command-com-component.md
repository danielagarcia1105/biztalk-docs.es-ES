---
title: 'Comando AddResource: Componente de COM | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86a4f2fc-bbbe-4b4a-8008-2c79b3ebb6a1
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 757c6f334d5f3bc694b7db201467be80a3a0bc87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233956"
---
# <a name="addresource-command-com-component"></a>AddResource (comando): Componente de COM
Para agregar un componente COM no administrado a una aplicación de BizTalk, use la **AddResource** comando y especifique **BizTalk: com** para el parámetro de tipo. Ejecutar este comando agrega el componente COM a la base de datos de administración de BizTalk. Además, el componente COM aparece en la consola de administración de BizTalk Server, en la carpeta Recursos de la aplicación a la que lo agregó. Además, el componente se enumera cuando se usa el [comando ListApp](../core/listapp-command.md).  
  
> [!NOTE]
>  Si agrega un componente COM o COM+ de 64 bits sin administrar e intenta instalar la aplicación que incluye el componente COM o COM+ en un equipo de 32 bits, no se instalará el componente. Se instala únicamente en un equipo de 64 bits.  
  
## <a name="usage"></a>Uso  
 **BTSTask AddResource** [**/ApplicationName:***valor*] **/Type:System.BizTalk:Com** [**/Overwrite**] **/Source:***valor* [**/Destination:***valor*] [**/Options:Regsvr32OnInstall** ] [**/Server:***valor*] [**/Database:***valor*]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|No|Nombre de la aplicación de BizTalk a la que se agrega el componente COM. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo.|  
|**/ Escriba** (o **/T**, vea la sección Comentarios)|Sí|**BizTalk: com** (este valor no distingue entre mayúsculas y minúsculas).|  
|**/ Sobrescribir** (o **/Ov**, vea la sección Comentarios)|No|Opción para actualizar un componente COM existente. Si no se especifica y ya existe un componente COM en la aplicación que tiene el mismo nombre de archivo que el componente COM que se agrega, se produce un error en la operación AddResource.|  
|**/ Origen** (o **/So**, vea la sección Comentarios)|Sí|Ruta completa del archivo .dll del componente COM, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
|**/ Destino** (o **/De**, vea la sección Comentarios)|No|Ruta completa de la ubicación en la que se va a copiar el archivo .dll del componente COM cuando se instale la aplicación desde el archivo .msi. Si no se proporciona, el archivo no se copia al sistema de archivos local durante instalación; por tanto, el componente no se puede agregar al Registro de Windows durante instalación. Si la ruta incluye espacios, la debe encerrar entre comillas dobles ("). Si especifica el Regsvr32OnInstallOption, también debe especificar Destino.|  
|**/ Opciones de** (o **/Op**, vea la sección Comentarios)|No|**Regsvr32OnInstall.** Especificar que se agregue el componente COM al Registro de Windows cuando se instale la aplicación desde el archivo .msi. Si especifica esta opción, también debe especificar Destino.|  
|**/ Servidor** (o **/Se**, vea la sección Comentarios)|No|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|No|Nombre de la base de datos de administración de BizTalk. Si no se proporciona, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **Tipo de BTSTask AddResource /ApplicationName:MyApplication /: BizTalk: com / Overwrite/Source: "C:\Source Components\COM.dll" /Destination: "C:\New Components\COM.dll" /Options:Regsvr32OnInstall /Server:MyDatabaseServer /Database: BizTalkMgmtDb**  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [AddResource (comando)](../core/addresource-command.md)   
 [Cómo agregar un ensamblado de .NET a una aplicación](../core/how-to-add-a-net-assembly-to-an-application.md)