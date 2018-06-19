---
title: Comando ListApp | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5329dd55-4ce7-46d2-8983-90ac33725055
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 868e1606ae994a39fb8b558cdf2f282be12e5ad4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262500"
---
# <a name="listapp-command"></a>ListApp (comando)
Imprime en la consola una lista de todos los artefactos de recurso de una aplicación de BizTalk, junto con el identificador local único (LUID) y el tipo de cada el artefacto. Un artefacto de recurso es aquella que puede agregar a una aplicación de BizTalk mediante el [comando AddResource](../core/addresource-command.md), como un ensamblado, una secuencia de comandos, un archivo, una directiva, un componente COM, un directorio virtual, un artefacto de BAM o un certificado. Estos artefactos de recurso también se muestran en el nodo Recursos de la consola de administración de BizTalk Server.  
  
 Si especifica el parámetro ResourceSpec para este comando, la misma información se escribe en un archivo .xml. Puede usar este archivo .xml con el **ExportApp** comando para exportar un subconjunto de artefactos de una aplicación a un archivo .msi, tal y como se describe en [comando ExportApp](../core/exportapp-command.md).  
  
 Para directorios virtuales, este comando sustituye el nombre de host del servidor Web por "localhost" Si utiliza el archivo generado por el parámetro ResourceSpec con el comando ExportApp, se edita manualmente el archivo para reemplazar "localhost" por el nombre de host y el número de puerto si existe el servidor Web en un equipo remoto. En caso contrario, el directorio virtual y sus contenidos no se agregarán al archivo .msi de aplicación.  
  
 Ejemplo: http://MyWebServer:80/MyVirtualDirectory.  
  
## <a name="usage"></a>Uso  
 **BTSTask ListApp** [**/ApplicationName:***valor*] [**/resourcespec:***valor*] [  **/Server :***valor*] [**/Database:***valor*]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|No|Nombre de la aplicación de BizTalk para la que se enumeran los artefactos. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").  Si no se especifica este parámetro, se utiliza la aplicación predeterminada.|  
|**/ ResourceSpec** (o **/r**, vea la sección Comentarios)|No|Ruta completa de acceso del archivo .xml que se va a generar con este comando. Este archivo mostrará los artefactos de la aplicación junto con el LUID y el tipo de cada uno de ellos. Ejemplo: C:\Artifacts\MyArtifacts.xml. Si la ruta de acceso incluye espacios, debe ir entre comillas dobles ("). Si existe un archivo que ya tiene el mismo nombre de archivo y la misma ruta de acceso, se sobrescribe.|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|No|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/D**, vea la sección Comentarios)|No|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **BTSTask ListApp /ApplicationName:MyApplication /ResourceSpec:C:\Artifacts\MyArtifacts.xml**  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)