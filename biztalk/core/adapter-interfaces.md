---
title: Interfaces de adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7398aeb-7c1c-400e-a552-d0ab39e55a0b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717adcf5d4a706a7cc072b42b224ab0f9f8cc6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225492"
---
# <a name="adapter-interfaces"></a>Interfaces de adaptador
Hay tres interfaces que los adaptadores personalizados deben implementar y dos interfaces que son opcionales.  
  
## <a name="mandatory-interfaces"></a>Interfaces obligatorias  
 Todos los adaptadores deben implementar las interfaces siguientes.  
  
### <a name="ibasecomponent"></a>IBaseComponent  
 Esta información de la interfaz del **nombre**, **versión**, y **descripción** del adaptador.  
  
### <a name="ibttransport"></a>IBTTransport  
 Esta información de la interfaz del **tipo de transporte** y **ClassID** del adaptador.  
  
### <a name="ibtbatchcallback"></a>IBTBatchCallback  
 Es una interfaz de devolución de llamada a través de la que el adaptador recibe información de estado y de errores de un lote de mensajes enviados al motor de mensajería.  
  
## <a name="optional-interfaces"></a>Interfaces opcionales  
 Los adaptadores, en función de sus necesidades, puede que implementen o no las interfaces siguientes.  
  
### <a name="ipersistpropertybag"></a>IPersistPropertyBag  
 Es una interfaz de configuración a través de la que se entrega la configuración del controlador al adaptador. Solo es necesaria para los adaptadores que tienen información de configuración del controlador.  
  
### <a name="ibttransportcontrol"></a>IBTTransportControl  
 Esta interfaz se usa para inicializar y finalizar un adaptador. El proxy de transporte del adaptador se pasa al adaptador a través de esta interfaz. Esta interfaz no es necesaria para los adaptadores aislados.