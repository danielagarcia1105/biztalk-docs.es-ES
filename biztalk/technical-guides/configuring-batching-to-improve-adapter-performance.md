---
title: Configurar el procesamiento por lotes para mejorar el rendimiento del adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65589925-af94-45f1-b501-37c21618b2cf
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dbee8e5b238af0a6dc7f15d54b85d85e0c4b26c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300388"
---
# <a name="configuring-batching-to-improve-adapter-performance"></a>Configurar el procesamiento por lotes para mejorar el rendimiento del adaptador
La forma en que un adaptador procesa un lote puede tener un efecto significativo en el rendimiento. Puesto que hay un retraso fijo con cada transacción, debe tratar de minimizar el número de transacciones mediante la combinación de varias operaciones en un solo lote.  
  
 Si va a enviar mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en lotes, no limitan el tamaño del lote basándose solo en el número de mensajes. Por ejemplo, si el tamaño del lote es dos y el adaptador obtiene cuatro mensajes de tamaño de 4 KB, 8 KB, 1 MB y 5 MB respectivamente, será el primer lote del tamaño de 12 KB y el segundo lote será de 6 MB de tamaño. Puesto que el motor de mensajería de BizTalk procesa todos los mensajes en un solo lote de forma secuencial, el segundo lote de este ejemplo se procesará mucho más lento que el primero. El efecto de esto es el rendimiento reducido.  
  
 Para resolver este problema, se recomienda que procesa por lotes según el número de mensajes y el número total de bytes en el lote (es decir, el tamaño de lote en bytes). No hay ningún número óptimo de bytes totales. Sin embargo, en un escenario de procesamiento normal, si el tamaño del lote supera 1 MB, iniciará encontrar rendimiento y simultaneidad deficiente.  
  
 Adaptadores generalmente procesan mensajes de tamaño variable en el entorno de producción. Los tamaños de los mensajes entrantes son propensos a variar considerablemente. Como resultado, use siempre mensaje recuento y los bytes totales para generar el lote.