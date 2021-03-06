---
title: 'AddResource (comando): Directiva | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5effcbe-bf53-4741-8d5e-227620d4d84d
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43b90d74a177d11b478aff3302aa31306188cbcd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993661"
---
# <a name="addresource-command-policy"></a>AddResource (comando): directiva
Para agregar una directiva a una aplicación de BizTalk, usa el **AddResource** comando y especifique **BizTalk: Rules** para el parámetro de tipo. Ejecutar este comando agrega la directiva a la base de datos de administración de BizTalk. Además, la directiva aparece en la consola de administración de BizTalk Server en la carpeta Directivas de la aplicación a la que la agregó. Además, la directiva aparece cuando se usa el [comando ListApp](../core/listapp-command.md).  
  
 Para que este comando se ejecute correctamente, la directiva debe existir en la base de datos del motor de reglas. Para obtener instrucciones sobre cómo importar una directiva a la base de datos de motor de reglas, consulte [cómo importar una directiva](../core/how-to-import-a-policy.md). Al agregar una directiva mediante el comando AddResource, también se agrega automáticamente cualquier vocabulario utilizado por la directiva.  
  
## <a name="usage"></a>Uso  
 **BTSTask AddResource** [**/ApplicationName:**<em>valor</em>] **/Type:System.BizTalk:Rules** [**/Overwrite**] **/Name:**<em>valor</em>**/Version:**<em>valor</em> [**/Server:**<em>valor</em> ] [**/Database:**<em>valor</em>]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|no|Nombre de la aplicación de BizTalk a la que se agrega la directiva. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo.|  
|**/ Escriba** (o **/T**, vea la sección Comentarios)|Sí|**BizTalk: Rules** (este valor no distingue mayúsculas de minúsculas).|  
|**/ Sobrescribir** (o **/O**, vea la sección Comentarios)|no|Opción para actualizar una directiva existente. Si no se especifica y ya existe una directiva en la aplicación que tiene el mismo nombre que la directiva que se agrega, se produce un error en la operación AddResource.|  
|**/ Nombre** (o **/N**, vea la sección Comentarios)|Sí|Nombre de la directiva.|  
|**/ Versión** (o **/V**, vea la sección Comentarios)|Sí|Número de versión de la directiva en el formato número.número.<br /><br /> Ejemplo: 1.0|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|no|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/D**, vea la sección Comentarios)|no|Nombre de la base de datos de administración de BizTalk. Si no se proporciona, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **Tipo de BTSTask AddResource /ApplicationName:MyApplication /: BizTalk: Rules / Overwrite /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Notas  
 Si se ha implementado MyPolicy, el comando mencionado anteriormente devolverá lo siguiente:  
  
 Error: Error al agregar los recursos.  
  
 Error en la validación de 1 recurso.  
  
 No puede sobrescribirse la directiva de reglas "MyPolicy" versión 1.0. Ya está en producción.  
  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [AddResource (comando)](../core/addresource-command.md)   
 [Cómo agregar una directiva a una aplicación](../core/how-to-add-a-policy-to-an-application.md)