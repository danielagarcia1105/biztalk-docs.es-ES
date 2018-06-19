---
title: Cómo configurar la forma compensar | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Compensate shape [Orchestration Designer], about Compensate shape
- Compensate shape [Orchestration Designer]
- compensations, Compensate shape [Orchestration Designer]
- configuring [Orchestration Designer], Compensate shape
- Compensate shape [Orchestration Designer], configuring
ms.assetid: 9f06289e-4d11-4864-9851-c210276865a7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 059ac58d95d33234737033c00c4a6a2a36e256f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248284"
---
# <a name="how-to-configure-the-compensate-shape"></a>Cómo configurar la forma Compensar
Si está utilizando transacciones anidadas en la orquestación, puede agregar un **compensar** forma en el bloque de compensación o un bloque de excepción de la transacción. Esto permite que la orquestación lleve a cabo explícitamente compensaciones en una transacción anidada. Especifica qué transacciones quiere que se compensen en el **compensar** forma como cualquier otro código de compensación de la transacción anidada se ejecutará, siempre que ésta se llevó a cabo correctamente.  
  
> [!NOTE]
>  El **compensación** propiedad hace referencia al identificador único del ámbito de transacción, no hace referencia al nombre del ámbito.  
  
 Si desea compensar más de una transacción anidada, agregar otro **compensar** forma por cada transacción.  
  
 Ya no **compensar** forma es necesaria si no hay ningún otro código de compensación en una transacción externa; se ejecutará automáticamente el código de compensación de las transacciones anidadas. El **compensar** forma le proporciona control sobre el proceso de por lo que le permite decidir si desea o no se compensen las transacciones anidadas.  
  
### <a name="to-configure-a-compensate-shape"></a>Para configurar una forma Compensar  
  
-   En la ventana Propiedades, seleccione el bloque de compensación para llamar desde el **compensación** lista desplegable.  
  
     La lista desplegable mostrará todas las transacciones que pueden compensarse, lo que incluye la transacción actual y todas las transacciones secundarias inmediatas respecto de la actual. Si no puede ver una transacción que esperaba, podría deberse a la relación de las transacciones.  
  
    > [!NOTE]
    >  No es posible compensar la transacción actual desde dentro del cuerpo de la transacción.  Puede compensarla desde el bloque de compensación o desde un bloque de excepción de la transacción.  
  
     Si opta por compensar la transacción actual, se invocará el controlador predeterminado y no un bloque de compensación explícito (si hubiera uno). Se trata de un mecanismo para compensar automáticamente las transacciones anidadas de forma directa que se han completado correctamente.