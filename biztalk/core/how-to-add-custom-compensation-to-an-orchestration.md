---
title: Cómo agregar la compensación personalizada a una orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- Compensate shape [Orchestration Designer]
- Compensate shape [Orchestration Designer], orchestrations
- Compensation property
- orchestrations, transactional
- orchestrations, customizing
- customizing, orchestrations
- Compensate shape [Orchestration Designer], custom compensation
ms.assetid: d153498d-8f98-42ae-90b9-e3083d669aef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eadb9cba6e5a49be516a8095b01f93ca7a490f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248124"
---
# <a name="how-to-add-custom-compensation-to-an-orchestration"></a>Cómo agregar la compensación personalizada a una orquestación
Una transacción de orquestación configurada como de larga ejecución puede incluir código de compensación personalizada para invertir o deshacer los efectos de la transacción. Si la orquestación se ha completado correctamente y se ha llamado a otra orquestación, la orquestación de llamada puede invocar su bloque de compensación mediante una **compensar** forma.  
  
### <a name="to-specify-that-an-orchestration-will-use-custom-compensation"></a>Para especificar que una orquestación utilice la compensación personalizada  
  
1.  En la ventana Vista orquestación, seleccione **propiedades de orquestación**.  
  
2.  En la ventana Propiedades, seleccione **personalizado** en la lista desplegable para la **compensación** propiedad.  
  
     El **compensación** ficha aparece junto a la **orquestación** ficha situada en la parte inferior de la superficie de diseño.  
  
### <a name="to-design-custom-compensation-for-an-orchestration"></a>Para diseñar una compensación personalizada para una orquestación  
  
1.  Haga clic en el **compensación** ficha situada en la parte inferior de la superficie de diseño.  
  
     El **superficie de diseño de compensación** aparece.  
  
2.  Agregar formas a la **superficie de diseño de compensación** tal y como lo haría en la **superficie de diseño de orquestación**.  
  
     Para obtener más información, consulte [agregar formas a orquestaciones](../core/how-to-add-shapes-to-orchestrations.md).  
  
## <a name="see-also"></a>Vea también  
 [Realizar orquestaciones transaccionales](../core/making-orchestrations-transactional.md)