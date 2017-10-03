---
title: 'Resultados de pruebas: Indicadores clave de rendimiento de red | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9bdbc2df-9d19-4ae8-b540-ec1b9a7cdbe9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb4e10c739178e6cd923f65b51f982e05ab7f56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="test-results-networking-key-performance-indicators"></a>Resultados de pruebas: Indicadores clave de rendimiento de red
En este tema se resume observado durante los escenarios de prueba la indicadores de rendimiento de clave de red (KPI). Estas pruebas evalúan el rendimiento de la red según lo medido por la **\Network interfaz (\*) \Bytes totales/seg.** contador y mediante la medición del monitor de rendimiento del **SQL red\Bytes totales/seg. (Avg)**  devuelto por el controlador de pruebas de carga de VSTS 2008.  
  
## <a name="summary-of-network-key-performance-indicators"></a>Resumen de indicadores clave de rendimiento de red  
 **Comparación de los indicadores clave de rendimiento de las redes:** rendimiento de la red para que BizTalk Server que se ejecutan en máquinas virtuales de Hyper-V se observó en el intervalo de aproximadamente 70-96% del rendimiento de red de los servidores físicos de BizTalk , dependiendo del entorno de prueba determinada. Rendimiento de la red de SQL Server que se ejecuta en una máquina virtual de Hyper-V se observó en el intervalo de 68 y 81% aproximadamente del rendimiento de red obtenido en el servidor físico de SQL, nuevo según el entorno de prueba determinada. Las diferencias en el rendimiento de la red observado se pueden atribuir a los requisitos de recursos del hipervisor de Hyper-V.  
  
 Siga los pasos de [optimizaciones de red](../technical-guides/network-optimizations.md) para maximizar el rendimiento de red de máquinas virtuales de Hyper-V, medido por **\Network interfaz (\*) \Bytes totales/seg.**  
  
 El siguiente gráfico muestra el rendimiento de la red en las diferentes plataformas de prueba:  
  
 ![Indicadores clave de rendimiento de red](../technical-guides/media/networkkpi.gif "NetworkKPI")  
  
 La siguiente tabla muestra el rendimiento relativo de recopilados de KPI para cada configuración. Cada conjunto de resultados se calcula como un porcentaje de la configuración de línea de base KPI  
  
|KPI|Virtual de BizTalk o física SQL|Virtual SQL de BizTalk y virtuales en Hosts independientes|Virtual de BizTalk/Virtual de SQL en el entorno consolidado|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|\Network interfaz (*) \Bytes totales/seg. (promedio Total en todos los servidores de BizTalk)|96%|82.1%|70.2%|  
|SQL red bytes totales/seg (Avg)|95.5%|81.2%|68.4%|  
  
 Para obtener más información acerca de cómo evaluar el rendimiento de red, consulte la **medir el rendimiento de red** sección del tema [lista de comprobación: medir el rendimiento en Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).