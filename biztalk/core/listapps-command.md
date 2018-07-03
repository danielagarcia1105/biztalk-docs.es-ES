---
title: ListApps (comando) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5eb0af-e153-4639-a6c0-56c951827c7c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0206471feefe8ffe52ec2045ede865bb064ea452
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974013"
---
# <a name="listapps-command"></a>ListApps (comando)
Imprime en la consola el nombre y la descripción de todas las aplicaciones de BizTalk de la base de datos de administración de BizTalk especificada.  
  
## <a name="usage"></a>Uso  
 **BTSTask ListApps** [**/Server:**<em>valor</em>] [**/Database:**<em>valor</em>]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Descripción|  
|---------------|--------------|-----------------|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|no|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/D**, vea la sección Comentarios)|no|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **BTSTask ListApps**  
  
## <a name="remarks"></a>Notas  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)