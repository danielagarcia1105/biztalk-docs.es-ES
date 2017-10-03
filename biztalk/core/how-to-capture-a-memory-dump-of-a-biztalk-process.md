---
title: "Cómo capturar un volcado de memoria de un proceso de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8053fcf3-b331-4245-b3c3-21290463e0c0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f87ad0f4a3eb3a49ea789d45a707bbc8b46cb4c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-capture-a-memory-dump-of-a-biztalk-process"></a>Cómo capturar un volcado de memoria de un proceso de BizTalk
Es posible que, en determinadas circunstancias, sea necesario capturar un volcado de memoria de un proceso que se está ejecutando en un servidor de BizTalk Server para realizar un análisis en profundidad del proceso. A continuación se indican las situaciones que pueden requerir el análisis de un volcado de memoria:  
  
-   Cuando no responde un proceso.  
  
-   Cuando un proceso está bloqueado.  
  
-   Cuando un proceso pierde memoria.  
  
 En esta sección se incluyen los pasos que se deberían seguir para capturar el tipo adecuado de volcado de memoria.  
  
## <a name="installation-of-the-iis-diagnostics-toolkit"></a>Instalación del Kit de herramientas de diagnóstico de IIS  
 Cada uno de los temas de esta sección requiere el uso de la **Debug Diagnostics Tool** del Kit de herramientas de diagnóstico de IIS para capturar un volcado de memoria. Para instalar el **Debug Diagnostics Tool** del Kit de herramientas de diagnóstico de IIS, siga estos pasos:  
  
1.  Descargar el Kit de herramientas de diagnóstico IIS de [herramientas de diagnóstico de los servicios de Internet Information Server](http://go.microsoft.com/fwlink/?LinkId=64426).  
  
2.  Haga doble clic en el **iisdiag.msi** paquete para iniciar el programa de instalación del Kit de herramientas de diagnóstico de IIS y elija la **personalizado** tipo de instalación.  
  
3.  En el **personalizada** cuadro de diálogo, asegúrese de que la opción para la **Debug Diagnostics Tool 1.0** está habilitada y complete los pasos del programa de instalación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo capturar un volcado de memoria de un proceso que no responde](../core/how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive.md)  
  
-   [Cómo capturar un volcado de memoria de un proceso que está bloqueado](../core/how-to-capture-a-memory-dump-of-a-process-that-is-crashing.md)  
  
-   [Cómo capturar un volcado de memoria de un proceso que pierde memoria](../core/how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory.md)  
  
-   [Cómo usar diagnósticos de depuración para analizar un volcado de memoria](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)