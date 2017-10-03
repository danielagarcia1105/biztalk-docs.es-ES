---
title: "Interfaces del motor de mensajería | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14241db3-edcf-4449-9ec8-2171a14496c0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a135505240e94fb42e5810a3e7ac71d4c99c34a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="messaging-engine-interfaces"></a>Interfaces del motor de mensajería
Existen tres interfaces públicas que los adaptadores pueden usar para permitir la interacción con el motor de mensajería. Se describen en las secciones siguientes.  
  
## <a name="ibttransportproxy"></a>IBTTransportProxy  
 Los adaptadores siempre interactúan con el motor de mensajería mediante su propio proxy de transporte. El proxy de transporte se usa para operaciones tales como la creación de lotes, la obtención del generador de mensajes y el registro de receptores aislados en el motor.  
  
## <a name="ibttransportbatch"></a>IBTTransportBatch  
 Esta interfaz la proporciona el motor de mensajería y define métodos que los adaptadores pueden usar para realizar operaciones en lotes de mensajes. El motor de mensajería procesa los lotes de manera asíncrona.  
  
## <a name="ibtdtccommitconfirm"></a>IBTDTCCommitConfirm  
 Los adaptadores que usan transacciones explícitas del Coordinador de transacciones distribuidas de Microsoft (MSDTC) con los lotes deben utilizar esta interfaz para notificar al motor cuál ha sido el resultado de la transacción mediante esta interfaz.