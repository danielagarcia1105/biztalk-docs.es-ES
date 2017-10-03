---
title: ExportBindings (comando) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6573142e-7ca7-4990-98e3-b7a54840da13
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f12e28b68698aeb42aefa387c94bd76470ecaf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="exportbindings-command"></a>ExportBindings (comando)
Exporta enlaces para un ensamblado, una aplicación o un grupo de BizTalk. También puede exportar enlaces de entidad global junto con el ensamblado, la aplicación o los enlaces de grupo. (Una entidad son todas las entidades, como socios comerciales de su organización que interactúan con una orquestación.)  
  
## <a name="usage"></a>Uso  
 **BTSTask ExportBindings /Destination:** *valor* [**/GroupLevel**] [**/ApplicationName:***valor*] [**/AssemblyName:***valor* ] &#124; [**/GlobalParties**] [**/Server:***valor*] [**/Database:***valor*]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Valor|  
|---------------|--------------|-----------|  
|**/ Destino** (o **/De**, vea la sección Comentarios)|Sí|Ruta completa del archivo de enlace que se va a crear, incluido el nombre de archivo. Si existe un archivo de enlace que ya tiene la misma ruta de acceso, se sobrescribe. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
|**/ GroupLevel** (o **/GR**, vea la sección Comentarios)|No|Cuando se especifica, se exportan todos los enlaces del grupo actual. Puede especificar sólo uno de estos tres parámetros: GroupLevel, ApplicationName o AssemblyName.|  
|**/ ApplicationName** (o **/Ap**, vea la sección Comentarios)|No|Nombre de la aplicación desde la que se exportan los enlaces. Debe existir la aplicación. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Para comprobar el nombre de la aplicación, puede usar el **ListApps** de comandos, como se describe en [ListApps (comando)](../core/listapps-command.md). Si no se especifica este parámetro, se utiliza la aplicación de BizTalk predeterminada. Puede especificar sólo uno de estos tres parámetros: GroupLevel, ApplicationName o AssemblyName.|  
|**/ AssemblyName** (o **/As**, vea la sección Comentarios)|No|Identificador local único (LUID) del ensamblado desde el que se exportan los enlaces. Puede ver la lista de LUID para los artefactos de una aplicación mediante la [comando ListApp](../core/listapp-command.md). Puede especificar sólo uno de estos tres parámetros: GroupLevel, ApplicationName o AssemblyName.|  
|**/ GlobalParties** (o **/GL**, vea la sección Comentarios)|No|Si se especifica, exporta la información de entidad global del grupo.|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|No|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|No|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **BTSTask ExportBindings /Destination: "C:\Binding Files\MyBindings.xml" GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)   
 [Exportar enlaces](../core/exporting-bindings6.md)