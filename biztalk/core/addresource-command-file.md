---
title: 'AddResource (comando): Archivo | Microsoft Docs'
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
ms.openlocfilehash: b4878e74d1c45e5d75280a5ce9daf5447ed1e905
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982445"
---
# <a name="addresource-command-file"></a>AddResource (comando): archivo
Para agregar un archivo a una aplicación de BizTalk, usa el **AddResource** comando y especifique **BizTalk: file** para el parámetro de tipo. Ejecutar este comando agrega el archivo a la base de datos de administración de BizTalk. Además, el archivo aparece en la consola de administración de BizTalk Server en la carpeta Recursos de la aplicación a la que lo agregó. Además, el archivo aparece cuando se usa el [comando ListApp](../core/listapp-command.md).  
  
## <a name="usage"></a>Uso  
 **BTSTask AddResource** [**/ApplicationName:**<em>valor</em>] **/Type:System.BizTalk:File** [**/Overwrite**] **/Source:**<em>valor</em> [**/Destination:**<em>valor</em>] [**/Server:**  <em>valor</em>] [**/Database:**<em>valor</em>]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|no|Nombre de la aplicación de BizTalk a la que se agrega el archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk.|  
|**/ Escriba** (o **/T**, vea la sección Comentarios)|Sí|**BizTalk: file** (este valor no distingue mayúsculas de minúsculas).|  
|**/ Sobrescribir** (o **/O**, vea la sección Comentarios)|no|Opción para actualizar un archivo existente. Si no se especifica y ya existe un archivo en la aplicación que tiene el mismo nombre que el archivo que se agrega, se produce un error en la operación AddResource.|  
|**/ Origen** (o **/So**, vea la sección Comentarios)|Sí|Ruta completa del archivo de ensamblado, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
|**/ Destino** (o **De**, vea la sección Comentarios)|no|Ruta completa de la ubicación en la que se va a copiar el archivo cuando se instale la aplicación desde el archivo .msi. Si la ruta incluye espacios, la debe encerrar entre comillas dobles ("). Si no se proporciona, el archivo no se copia al sistema de archivos local durante instalación.|  
|**/ Servidor** (o **/Se**, vea la sección Comentarios)|no|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|no|Nombre de la base de datos de administración de BizTalk. Si no se proporciona, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **Tipo de BTSTask AddResource /ApplicationName:MyApplication /: BizTalk: File / Overwrite/Source: "C:\Source Files\File.txt" /Destination: "C:\New Files\File.txt" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Notas  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [AddResource (comando)](../core/addresource-command.md)   
 [Cómo agregar un ensamblado .NET a una aplicación](../core/how-to-add-a-net-assembly-to-an-application.md)