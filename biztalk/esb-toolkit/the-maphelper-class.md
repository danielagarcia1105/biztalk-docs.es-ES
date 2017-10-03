---
title: La clase MapHelper | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c552c066-835f-4515-939f-dd465a7a5ed0
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de74610c40b37560abcbce040d80320525f0a21c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-maphelper-class"></a>La clase MapHelper
Use la **MapHelper** clase para realizar transformaciones directamente sin usar la transformación del servicio Web.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] instalador instala y registra el ensamblado **Microsof.Practices.ESB.Transform.dll** con el **MapHelper** clase en la memoria caché global de ensamblados.  
  
 El **MapHelper** clase expone dos métodos públicos:  
  
-   **TransformMessage**. Este método toma como parámetros de una cadena que contiene el mensaje que se va a transformar y una cadena que contiene el nombre completo de un mapa que se implementan en BizTalk. El método devuelve una cadena que contiene el documento transformado.  
  
-   **TransformMessageStream**. Este método toma como parámetros de una secuencia que contiene el mensaje que se va a transformar y una cadena que contiene el nombre completo de un mapa que se implementan en BizTalk. El método devuelve una cadena que contiene el documento transformado.