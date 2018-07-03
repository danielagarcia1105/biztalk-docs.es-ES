---
title: ExportBindings (comando) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6573142e-7ca7-4990-98e3-b7a54840da13
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 478a1c75a1e47a801d47ef9f9481a00931d37ecf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971837"
---
# <a name="exportbindings-command"></a>ExportBindings (comando)
Exporta enlaces para un ensamblado, una aplicación o un grupo de BizTalk. También puede exportar enlaces de entidad global junto con el ensamblado, la aplicación o los enlaces de grupo. (Una entidad son todas las entidades, como socios comerciales de su organización que interactúan con una orquestación.)  
  
## <a name="usage"></a>Uso  
 **BTSTask ExportBindings /Destination:** *valor* [**/GroupLevel**] [**/ApplicationName:**<em>valor</em>] [**/AssemblyName:**<em>valor</em> ] &#124; [**/GlobalParties**] [**/Server:**<em>valor</em>] [**/Database:**<em>valor</em>]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Valor|  
|---------------|--------------|-----------|  
|**/ Destino** (o **/De**, vea la sección Comentarios)|Sí|Ruta completa del archivo de enlace que se va a crear, incluido el nombre de archivo. Si existe un archivo de enlace que ya tiene la misma ruta de acceso, se sobrescribe. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
|**/ GroupLevel** (o **/GR**, vea la sección Comentarios)|no|Cuando se especifica, se exportan todos los enlaces del grupo actual. Puede especificar solo uno de estos tres parámetros: GroupLevel, ApplicationName o AssemblyName.|  
|**/ ApplicationName** (o **/Ap**, vea la sección Comentarios)|no|Nombre de la aplicación desde la que se exportan los enlaces. Debe existir la aplicación. Si el nombre incluye espacios, debe encerrar entre comillas dobles ("). Para comprobar el nombre de la aplicación, puede usar el **ListApps** de comandos, como se describe en [ListApps (comando)](../core/listapps-command.md). Si no se especifica este parámetro, se utiliza la aplicación de BizTalk predeterminada. Puede especificar solo uno de estos tres parámetros: GroupLevel, ApplicationName o AssemblyName.|  
|**/ AssemblyName** (o **/As**, vea la sección Comentarios)|no|Identificador local único (LUID) del ensamblado desde el que se exportan los enlaces. Puede ver la lista de LUID para los artefactos de una aplicación mediante el uso de la [comando ListApp](../core/listapp-command.md). Puede especificar solo uno de estos tres parámetros: GroupLevel, ApplicationName o AssemblyName.|  
|**/ GlobalParties** (o **/GL**, vea la sección Comentarios)|no|Si se especifica, exporta la información de entidad global del grupo.|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|no|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|no|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **BTSTask ExportBindings /Destination: "C:\Binding Files\MyBindings.xml" GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Notas  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)   
 [Exportación de enlaces](../core/exporting-bindings6.md)