---
title: Elemento estructural de mensajes de conjunto de transacciones de EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caea8408-c09c-4525-a9c9-18abe4432594
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d49288e9a311c9766e61fe985b9e279a8660f4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239188"
---
# <a name="edi-transaction-set-message-structural-element"></a>Elemento estructural de mensajes de conjunto de transacciones de EDI
Los conjuntos de transacciones (en la codificación X12) y los mensajes (en la codificación EDIFACT) contienen segmentos que forman los datos del mensaje. Un conjunto de transacciones está constituido por un encabezado, una colección de segmentos de datos y un finalizador. En definitiva, contiene todos los detalles que resultan necesarios para procesar la transacción.  
  
 Un conjunto de transacciones debe empezar con un encabezado de conjunto de transacciones ST (en X12) o un encabezado de mensaje UNH (en EDIFACT). Para terminar, utiliza un finalizador de conjunto de transacciones SE (en X12) o un finalizador de mensaje UNT (en EDIFACT). El finalizador proporciona un número de los segmentos de datos, en el que se incluyen los segmentos del encabezado y del finalizador.  
  
 Un conjunto de transacciones puede contener uno o varios bucles, los cuales resultan necesarios para repetir una colección de segmentos relacionados.