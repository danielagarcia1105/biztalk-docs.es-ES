---
title: 'El comando AddResource: Archivo | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9635e43-af26-48d3-af0e-df245a8955e7
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92ed0b99c942adbb63fd7ca3bd2e29cc1ba040c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230308"
---
# <a name="addresource-command-file"></a>AddResource (comando): archivo
Para agregar un archivo a una aplicación de BizTalk, use la **AddResource** comando y especifique **BizTalk: file** para el parámetro de tipo. Ejecutar este comando agrega el archivo a la base de datos de administración de BizTalk. Además, el archivo aparece en la consola de administración de BizTalk Server en la carpeta Recursos de la aplicación a la que lo agregó. Además, el archivo aparece cuando se usa el [comando ListApp](../core/listapp-command.md).  
  
## <a name="usage"></a>Uso  
 **BTSTask AddResource** [**/ApplicationName:***valor*] **/Type:System.BizTalk:File** [**/Overwrite**] **/Source:***valor* [**/Destination:***valor*] [**/Server:**  *valor*] [**/Database:***valor*]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|No|Nombre de la aplicación de BizTalk a la que se agrega el archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk.|  
|**/ Escriba** (o **/T**, vea la sección Comentarios)|Sí|**BizTalk: file** (este valor no distingue entre mayúsculas y minúsculas).|  
|**/ Sobrescribir** (o **/o**, vea la sección Comentarios)|No|Opción para actualizar un archivo existente. Si no se especifica y ya existe un archivo en la aplicación que tiene el mismo nombre que el archivo que se agrega, se produce un error en la operación AddResource.|  
|**/ Origen** (o **/So**, vea la sección Comentarios)|Sí|Ruta completa del archivo de ensamblado, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
|**/ Destino** (o **Alemania**, vea la sección Comentarios)|No|Ruta completa de la ubicación en la que se va a copiar el archivo cuando se instale la aplicación desde el archivo .msi. Si la ruta incluye espacios, la debe encerrar entre comillas dobles ("). Si no se proporciona, el archivo no se copia al sistema de archivos local durante instalación.|  
|**/ Servidor** (o **/Se**, vea la sección Comentarios)|No|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|No|Nombre de la base de datos de administración de BizTalk. Si no se proporciona, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **Tipo de BTSTask AddResource /ApplicationName:MyApplication /: BizTalk: File / Overwrite/Source: "C:\Source Files\File.txt" /Destination: "C:\New Files\File.txt" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [AddResource (comando)](../core/addresource-command.md)   
 [Cómo agregar un ensamblado de .NET a una aplicación](../core/how-to-add-a-net-assembly-to-an-application.md)