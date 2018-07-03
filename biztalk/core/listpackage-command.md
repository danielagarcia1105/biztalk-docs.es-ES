---
title: ListPackage (comando) | Microsoft Docs
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
ms.openlocfilehash: 7c2469a509545dffc80a79a61a5f8f761f5bb724
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970469"
---
# <a name="listpackage-command"></a>ListPackage (comando)
Enumera los artefactos contenidos en un archivo .msi generado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="usage"></a>Uso  
 **BTSTask ListPackage** [**/paquete:**<em>valor</em>]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Descripción|  
|---------------|--------------|-----------------|  
|**/ Paquete** o **/P**|Sí|Nombre y ruta del archivo .msi. Ejemplo: C:\MSI\MyApplication.msi. Si la ruta de acceso incluye espacios, debe estar entre comillas dobles (").|  
  
## <a name="sample"></a>Ejemplo  
 **ListPackage /Package: "C:\My MSI msi\miaplicación. msi"**  
  
## <a name="remarks"></a>Notas  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)