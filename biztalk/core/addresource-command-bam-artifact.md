---
title: 'AddResource (comando): Artefacto de BAM | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9de7a82-9b06-4d50-9678-73140e80d0af
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abbd1e76204db4e642f0bd17e09b1d6f4b8b1773
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004117"
---
# <a name="addresource-command-bam-artifact"></a>AddResource (comando): Artefacto de BAM
Para agregar un artefacto de BAM a una aplicación de BizTalk, usa el **AddResource** comando y especifique **BizTalk: BAM** para el parámetro de tipo. Ejecutar este comando agrega el archivo de artefacto de BAM a la base de datos de administración de BizTalk. Además, el artefacto de BAM aparece en la consola de administración de BizTalk Server en la carpeta Recursos de la aplicación a la que lo agregó. Además, el archivo aparece cuando se usa el [comando ListApp](../core/listapp-command.md).  
  
 Agregar una definición de BAM mediante el comando AddResource no implementa la definición de BAM. Sin embargo, al importar un archivo .msi que incluye una definición de BAM a una aplicación mediante el Asistente para importación, la definición de BAM se implementa en el equipo local.  
  
## <a name="usage"></a>Uso  
 **BTSTask AddResource** [**/ApplicationName:**<em>valor</em>] **/Type:System.BizTalk:Bam**[**/Overwrite**] **/Source:**<em>valor</em> [**/Destination:**<em>valor</em>] [**/Server:**  <em>valor</em>] [**/Database:**<em>valor</em>]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|no|Nombre de la aplicación de BizTalk a la que se agrega el artefacto de BAM. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo.|  
|**/ Escriba** (o **/T**, vea la sección Comentarios)|Sí|**BizTalk: BAM** (este valor no distingue mayúsculas de minúsculas).|  
|**/ Sobrescribir** (o **/O**, vea la sección Comentarios)|no|Opción para actualizar un artefacto de BAM existente. Si no se especifica y ya existe un artefacto en la aplicación que tiene el mismo nombre que el artefacto de BAM que se agrega, se produce un error en la operación AddResource.|  
|**/ Origen** (o **/So**, vea la sección Comentarios)|Sí|Ruta completa del archivo de artefacto de BAM, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
|**/ Destino** (o **De**, vea la sección Comentarios)|no|Ruta completa de la ubicación en la que se va a copiar el archivo de artefacto de BAM cuando se instale la aplicación desde el archivo .msi. Si no se proporciona, el archivo no se copia al sistema de archivos local durante instalación. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
|**/ Servidor** (o **/Se**, vea la sección Comentarios)|no|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|no|Nombre de la base de datos de administración de BizTalk. Si no se proporciona, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **Tipo de BTSTask AddResource /ApplicationName:MyApplication /: BizTalk: BAM / Overwrite/Source: "C:\Source BAMfiles\MyBAMfile.xml" /Destination: "C:\New BAMfiles\MyBAMfile.xml" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Notas  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [AddResource (comando)](../core/addresource-command.md)   
 [Cómo agregar un artefacto de BAM a una aplicación](../core/how-to-add-a-bam-artifact-to-an-application.md)