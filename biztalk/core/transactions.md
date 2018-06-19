---
title: Las transacciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, transactions
- Orchestration Designer, BizTalk Server Orchestration Engine
- BizTalk Server Orchestration Engine
- Orchestration Designer, transactions
ms.assetid: d9a748c7-be9f-4965-a30f-6b05bd6b42a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74827beade56e6e54414371c9796454d3b48609e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279188"
---
# <a name="transactions"></a>Transactions
El Motor de orquestaciones de BizTalk Server administra el estado, aplica lógica empresarial e invoca las aplicaciones de admisión de procesos y/o conjuntos de transacciones complejos.  
  
 Los procesos empresariales se pueden componer como elementos discretos de trabajo mediante el uso de transacciones atómicas que revierten automáticamente todos los cambios en caso de errores o de una larga ejecución, las cuales pueden contener transacciones anidadas y usar el control de excepciones personalizadas para recuperarse de casos de error. Estas semánticas de transacciones se administran generalmente a través de la construcción Ámbito del Diseñador de orquestaciones.  
  
 Los procesos de larga duración pueden abarcar días, semanas y períodos más prolongados. Los procesos de larga duración normalmente utilizan la correlación para correlacionar mensajes que se reciben con los mensajes que se pueden enviar. El motor de orquestaciones normalmente deshidrata estas instancias para ahorrar recursos del sistema y rehidrata el proceso tras recibir estos mensajes correlacionados. El motor de orquestaciones guarda el estado de la orquestación para la base de datos de cuadro de mensajes en puntos de control conocidos para realizar la recuperación ante cualquier excepción de aplicación o del sistema.  
  
 El modelo de programación transaccional proporcionado por el motor de orquestaciones de BizTalk incluye la compatibilidad del control de excepciones y la recuperación de transacciones con errores, transacciones atómicas que revierten automáticamente sus acciones en caso de errores, o bien transacciones de larga ejecución que pueden contener otras transacciones, además del control de excepciones personalizadas.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Transacciones atómicas](../core/atomic-transactions.md)  
  
-   [Escenarios de uso de transacciones atómicas](../core/scenarios-using-atomic-transactions.md)  
  
-   [Transacciones de larga ejecución](../core/long-running-transactions.md)  
  
-   [Escenarios de uso de transacciones de larga ejecución](../core/scenarios-using-long-running-transactions.md)  
  
-   [Persistencia en orquestaciones](../core/persistence-in-orchestrations.md)