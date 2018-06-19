---
title: Transacciones orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- orchestrations, transactional
- Transaction Type property
ms.assetid: c4f0b6ca-d939-4d3a-b7ef-53c6aafdea9c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8c6fb466e0c3cc5cae4a076237d1dbc970b5794
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278740"
---
# <a name="transacted-orchestrations"></a>Orquestaciones configuradas como transacciones
Las orquestaciones pueden ser transaccionales, al igual que los ámbitos. De hecho, una orquestación puede considerarse un ámbito. Por lo general, se aplican las mismas reglas a las orquestaciones configuradas como transacciones que para los ámbitos configurados como orquestaciones.  
  
> [!NOTE]
>  Una diferencia entre las orquestaciones y otros ámbitos es que las orquestaciones no tienen controladores de excepciones.  
  
## <a name="orchestration-compensation"></a>Compensación de orquestación  
 Si el **tipo de transacción** propiedad para la orquestación está establecida en larga ejecución o atómica, también puede seleccionar un valor para el **compensación** propiedad, que puede ser predeterminado o personalizado.  
  
 Si selecciona **personalizado** para la compensación, un **compensación** ficha aparecerá junto a la superficie de diseño de orquestación. Tiene la misma apariencia que la superficie de diseño de orquestación y puede agregar formas y puertos a ella de la misma manera.  
  
 Las compensaciones solo tienen lugar en las orquestaciones a las que llaman otras orquestaciones. Puede compensar una instancia de orquestación específica mediante el uso de la **identificador** propiedad en el **orquestación de llamada** forma.  
  
> [!IMPORTANT]
>  Si existe una compensación en una orquestación de nivel superior, el motor de tiempo de ejecución la omitirá.  
  
## <a name="see-also"></a>Vea también  
 [Realizar orquestaciones transaccionales](../core/making-orchestrations-transactional.md)   
 [Uso de transacciones y control de excepciones](../core/using-transactions-and-handling-exceptions.md)