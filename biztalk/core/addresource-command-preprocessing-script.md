---
title: 'AddResource (comando): Script de preprocesamiento | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b4f66e5-1f40-4bc3-82a8-c27a0e435797
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29a19b090a0dbdb0b44cca43c6cf86cf2ea74a7e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990941"
---
# <a name="addresource-command-preprocessing-script"></a>AddResource (comando): Script de preprocesamiento
Para agregar un script de preprocesamiento para una aplicación de BizTalk, use el **AddResource** comando y especifique **BizTalk: preprocessingscript** para el parámetro de tipo. Ejecutar este comando agrega el archivo de secuencia de comandos a la base de datos de administración de BizTalk. Además, el archivo de secuencia de comandos aparece en la consola de administración de BizTalk Server, en la carpeta Recursos de la aplicación a la que lo agregó. Además, el archivo aparece cuando se usa el [comando ListApp](../core/listapp-command.md).  
  
 Una secuencia de comandos previa al procesamiento se ejecuta desde el archivo .msi antes de la instalación o importación de la aplicación, o después de la desinstalación. También puede utilizar BTSTask para agregar una secuencia de comandos que se ejecuta después de la instalación o importación de la aplicación, o antes de desinstalarla, como se describe en [AddResource (comando): secuencias de comandos](../core/addresource-command-postprocessing-script.md). Para obtener más información acerca de preprocesamiento y posteriores al procesamiento de secuencias de comandos, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).  
  
## <a name="usage"></a>Uso  
 **BTSTask AddResource** [**/ApplicationName:**<em>valor</em>] **/Type:System.BizTalk:PreProcessingScript**[**/Overwrite**] **/Source:**<em>valor</em> [**/Destination:**<em>valor</em>] [**/Server:**  <em>valor</em>] [**/Database:**<em>valor</em>] [**/Property: args = "**<em>lista de argumentos</em>**"** ]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|no|Nombre de la aplicación de BizTalk a la que se agrega la secuencia de comandos. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo.|  
|**/ Escriba** (o **/T**, vea la sección Comentarios)|Sí|**BizTalk: preprocessingscript** (este valor no distingue mayúsculas de minúsculas).|  
|**/ Sobrescribir** (o **/O**, vea la sección Comentarios)|no|Opción para actualizar una secuencia de comandos existente. Si no se especifica y ya existe un archivo de secuencia de comandos en la aplicación que tiene el mismo nombre que el archivo de secuencia de comandos que se agrega, se produce un error en la operación de agregar.|  
|**/ Origen** (o **/So**, vea la sección Comentarios)|Sí|Ruta completa del archivo de secuencia de comandos, incluido el nombre de archivo. Si hay espacios en la ruta de acceso, debe encerrarlo entre comillas dobles (").|  
|**/ Destino** (o **/De**, vea la sección Comentarios)|no|Ruta completa de la ubicación en la que se va a copiar el archivo de secuencia de comandos cuando se instale la aplicación desde el archivo .msi. Si no se proporciona, el archivo no se copia al sistema de archivos local durante instalación. Si esta secuencia de comandos se debe ejecutar durante la desinstalación de la aplicación, debería especificar Destino, ya que, de lo contrario, la secuencia de comandos no residirá en el sistema de archivos local y no se podrá ejecutar durante la desinstalación. Si hay espacios en la ruta de acceso, debe encerrarlo entre comillas dobles (").|  
|**/ Servidor** (o **/Se**, vea la sección Comentarios)|no|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|no|Nombre de la base de datos de administración de BizTalk. Si no se proporciona, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
|**/ Propiedad** (o **/P**, vea la sección Comentarios)|no|Ninguna o alguna propiedad de recurso que se pasará a la secuencia de comandos como argumento cuando se invoque la secuencia de comandos.|  
  
## <a name="sample"></a>Ejemplo  
 **Tipo de BTSTask AddResource /ApplicationName:MyApplication /: BizTalk: preprocessingscript / Overwrite/Source: "C:\Source Scripts\MyScript.vbs" /Destination: "C:\New Scripts\MyScript.vbs" /Server:MyDatabaseServer /Database:BizTalkMgmtDb / Property: args = "argumento1 argumento2"**  
  
## <a name="remarks"></a>Notas  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
 Se admiten las siguientes extensiones de archivos de script: .com, .exe, .bat, .cmd, .vbs, .vbe, .js, .jse, .wsf,. WSH.  
  
## <a name="see-also"></a>Vea también  
 [AddResource (comando)](../core/addresource-command.md)   
 [Cómo agregar una secuencia de comandos previa y posteriores al procesamiento a una aplicación](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)