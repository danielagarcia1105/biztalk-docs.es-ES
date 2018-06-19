---
title: Cómo ampliar el nivel de servidor BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- scaling, scaling up
ms.assetid: 9002006a-f301-4e15-94b9-6caffd7c527c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d55176072cd33e20dd1024bf2d9d1c39bca4567a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270140"
---
# <a name="scaling-up-the-biztalk-server-tier"></a>Escalar el nivel de BizTalk Server verticalmente
Para escalar el nivel de BizTalk verticalmente, debe actualizar la CPU, memoria, E/S y otros recursos. En la siguiente ilustración se muestra un ejemplo de cómo escalar verticalmente el nivel de BizTalk de un equipo con dos procesadores a un equipo con cuatro procesadores.  
  
 ![Escala &#45; una copia de seguridad BTS](../core/media/scaleupbts.gif "ScaleUpBTS")  
  
 Los escenarios para escalar el nivel de BizTalk verticalmente son similares a aquellos para escalar horizontalmente:  
  
-   BizTalk Server se convierte en un cuello de botella. Alguno de los problemas siguientes puede causar el cuello de botella:  
  
-   CPU: si el escenario utiliza canalizaciones, asignaciones u orquestaciones que hacen un uso intensivo de CPU, los servidores BizTalk Server no tendrán ningún espacio en cabeza adicional de CPU.  
  
-   Memoria y E/S: si los equipos existentes han alcanzado su límite máximo de memoria y E/S y el equipo debe actualizarse.  
  
-   Si escalar horizontalmente es demasiado costoso.  
  
-   Si escalar horizontalmente no resuelve el cuello de botella. Por ejemplo, escalar horizontalmente no soluciona los siguientes cuellos de botella:  
  
    -   Transformaciones de mensajes de gran tamaño  
  
    -   Gran número de mensajes por intercambio  
  
    -   Alta utilización de memoria por parte de algunos componentes de BTS, como las canalizaciones o los adaptadores,  
  
    -   Un protocolo de transporte, por ejemplo EDI  
  
## <a name="when-you-cant-scale-up-the-biztalk-tier"></a>Si no se puede escalar el nivel de BizTalk verticalmente  
  
-   En la base de datos de cuadro de mensaje se produce el cuello de botella.  
  
-   El cuello de botella se produce en un adaptador. Por ejemplo, si está utilizando un adaptador, después de aumentar el número de receptores de BizTalk, puede aumentar contención de bloqueo en la aplicación de back-end que extrae datos desde el adaptador de BizTalk. Esto limita su capacidad para escalar el adaptador verticalmente.  
  
## <a name="see-also"></a>Vea también  
 [Escalar horizontalmente el nivel de servidor BizTalk Server](../core/scaling-out-the-biztalk-server-tier.md)   
 [Cómo ampliar el nivel de SQL Server](../core/scaling-up-the-sql-server-tier.md)   
 [Escalar horizontalmente el nivel de servidor SQL](../core/scaling-out-the-sql-server-tier.md)   
 [Hosts de recepción escalados](../core/scaled-out-receiving-hosts.md)   
 [Hosts de procesamiento de escala horizontal](../core/scaled-out-processing-hosts.md)   
 [Hosts de envío de escala horizontal](../core/scaled-out-sending-hosts.md)   
 [Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [Bases de datos de escala horizontal](../core/scaled-out-databases.md)   
 [Agrupación en clústeres las bases de datos de servidor BizTalk Server](../core/clustering-the-biztalk-server-databases1.md)