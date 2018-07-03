---
title: AddApp (comando) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 445784f1-505b-4259-a3f4-6f0d61578b1c
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb47b817c0f48cb82337afc6c82613fc35df28f6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986581"
---
# <a name="addapp-command"></a>AddApp (comando)
Crea una aplicación nueva de BizTalk en la base de datos de administración de BizTalk. Puede ver la aplicación en el nodo Aplicaciones de la consola de administración de BizTalk Server. Puede agregar artefactos a la aplicación mediante el comando AddResource, como se describe en [AddResource (comando)](../core/addresource-command.md).  
  
## <a name="usage"></a>Uso  
 **/ ApplicationName BTSTask AddApp:** *valor* [**/Description:**<em>valor</em>] [**/predeterminado**] [**/ Servidor:**<em>valor</em>] [**/Database:**<em>valor</em>]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|Sí|Nombre de la aplicación de BizTalk para agregar. Si el nombre de la aplicación incluye espacios, debe estar entre comillas dobles (").|  
|**/ Default** (o **/Def**, vea la sección Comentarios)|no|Si se especifica, hace que la nueva aplicación sea la aplicación predeterminada para el grupo de BizTalk.|  
|**/ Descripción** (o **/Des**, vea la sección Comentarios)|no|Descripción de la aplicación. Debe ir entre comillas dobles (").|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|no|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|no|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **AddApp /ApplicationName:MyApplication /Description: "Mi aplicación de BizTalk"**  
  
## <a name="remarks"></a>Notas  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)   
 [Cómo crear una aplicación](../core/how-to-create-an-application.md)