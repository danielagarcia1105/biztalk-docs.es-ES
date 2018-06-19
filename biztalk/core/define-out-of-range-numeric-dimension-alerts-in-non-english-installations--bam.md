---
title: Cómo definir alertas fuera de intervalo numérico dimensión en instalaciones que no sean en inglés | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f1e0373-eadf-4c6d-9a38-a34d847f310f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea63008680c026eded843e32a7b2c6ff26dc0bf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238692"
---
# <a name="how-to-define-out-of-range-numeric-dimension-alerts-in-non-english-installations"></a>Cómo definir alertas de dimensiones numéricas fuera de rango en instalaciones cuyo idioma no sea el inglés
Al establecer alertas que incluyan una condición para un valor que está fuera de la dimensión de rango numérico en instalaciones que no sean en inglés, debe modificar manualmente la definición de BAM con la versión localizada de la cadena **fuera del intervalo**.  
  
 En la siguiente tabla se enumeran ejemplos de valores fuera de rango localizados.  
  
|Código de lenguaje|Cadena localizada|  
|-------------------|----------------------|  
|CN|超出范围|  
|DE|Außerhalb des gültigen Bereichs|  
|ES|Fuera de rango|  
|FR|hors limites|  
|IT|Fuori intervallo|  
|JA|範囲外|  
|KO|범위를 벗어남|  
|TW|超過範圍|  
  
### <a name="to-define-out-of-range-alerts-in-non-english-installations"></a>Para definir alertas fuera de rango en instalaciones que no estén en inglés  
  
1.  Desplácese hasta la carpeta que contenga el archivo xml de la definición de BAM.  
  
2.  Abra el archivo de la definición de BAM mediante un editor de texto o un editor XML.  
  
3.  Localice la dimensión de filtro para la dimensión numérica. Por ejemplo, si la dimensión se denomina **Alerts_NumDim**, debería buscar el siguiente nodo:  
  
    ```  
    <SlicerDimension Name="Alerts_NumDim">  
    <Level Name="(Out of Range)" />  
    </SlicerDimension>  
    ```  
  
4.  Cambiar el **fuera del intervalo** valor de cadena a la correspondiente cadena traducida.  
  
5.  Guarde el archivo e implemente la definición.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es un esquema de definición de BAM?](../core/what-is-a-bam-definition-schema.md)   
 [Cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md)