---
title: El comando AddApp | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 445784f1-505b-4259-a3f4-6f0d61578b1c
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a6b91faa406181db3e4195bf57baeb086a0b69e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="addapp-command"></a>AddApp (comando)
Crea una aplicación nueva de BizTalk en la base de datos de administración de BizTalk. Puede ver la aplicación en el nodo Aplicaciones de la consola de administración de BizTalk Server. Puede agregar artefactos a la aplicación mediante el comando AddResource, como se describe en [comando AddResource](../core/addresource-command.md).  
  
## <a name="usage"></a>Uso  
 **/ ApplicationName BTSTask AddApp:** *valor* [**/Description:***valor*] [**/predeterminado**] [**/ Servidor:***valor*] [**/Database:***valor*]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|Sí|Nombre de la aplicación de BizTalk para agregar. Si el nombre de la aplicación incluye espacios, debe ir entre comillas dobles (").|  
|**/ Predeterminado** (o **/def**, vea la sección Comentarios)|No|Si se especifica, hace que la nueva aplicación sea la aplicación predeterminada para el grupo de BizTalk.|  
|**/ Descripción** (o **/Des**, vea la sección Comentarios)|No|Descripción de la aplicación. Debe ir entre comillas dobles (").|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|No|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|No|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **AddApp /ApplicationName:MyApplication /Description: "Mi aplicación de BizTalk"**  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)   
 [Cómo crear una aplicación](../core/how-to-create-an-application.md)