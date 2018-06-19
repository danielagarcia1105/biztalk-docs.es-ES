---
title: El comando ListPackage | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be09b76b-429b-4639-89f0-1eadb0c851ce
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88fca4820dba7c04908e2b756fda0d1d25794a10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261964"
---
# <a name="listpackage-command"></a>ListPackage (comando)
Enumera los artefactos contenidos en un archivo .msi generado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="usage"></a>Uso  
 **BTSTask ListPackage** [**/paquete:***valor*]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Description|  
|---------------|--------------|-----------------|  
|**/ Paquete** o **/P**|Sí|Nombre y ruta del archivo .msi. Ejemplo: C:\MSI\MyApplication.msi. Si la ruta de acceso incluye espacios, debe ir entre comillas dobles (").|  
  
## <a name="sample"></a>Ejemplo  
 **ListPackage /Package: "C:\My MSI msi\miaplicación. msi"**  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)