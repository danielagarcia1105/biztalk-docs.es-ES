---
title: Elemento estructural de elemento de datos EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 775e8b87-b952-46d2-a506-5174d216a9aa
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 600edb30ff157a520ac67eebce58428a62e27c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-data-element-structural-element"></a>Elemento estructural de elemento de datos EDI
El elemento de datos es la unidad de datos principal del mensaje. Los elementos de datos se separan mediante el separador de elementos de datos, que es un asterisco de forma predeterminada para X12 y un signo más de manera predeterminada para EDIFACT. La opcionalidad de elementos de datos se define como obligatorio, opcional o condicional.  
  
 Un elemento de datos puede ser simple o compuesto. Los elementos de datos simples son numéricos y forman el nivel mínimo de datos. Los elementos de datos compuestos son concatenaciones de subelementos, que son elementos de datos simples separados por un separador de componentes. De forma predeterminada, el separador de componentes es el signo de dos puntos para X12 y EDIFACT.  
  
 Para mensajes codificados con EDIFACT, si los datos se van a enviar mediante EDI, es necesario enviar los caracteres definidos que se van a usar como separador. Debe usar un carácter de versión para indicar que el siguiente carácter no es un separador sino que forma parte de los datos. De forma predeterminada, el carácter de versión es el signo de interrogación de cierre (?).  
  
> [!NOTE]
>  No se admite un carácter de versión para X12. Si se encuentra un separador como parte de los datos de un intercambio codificado con X12, ya sea en la recepción o en el envío, el intercambio se suspenderá.