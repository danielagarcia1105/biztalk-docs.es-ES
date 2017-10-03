---
title: "Cómo identificar cuellos de botella en la base de datos BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6814c0df-3ce1-44f8-8e63-af6e23336c6d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8fa54379d6d314993ac33b7d6395f061e48849d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-identify-bottlenecks-in-the-bam-database"></a>Cómo identificar cuellos de botella en la base de datos de BAM
Para identificar cuellos de botella en la base de datos de BAM, realice los siguientes pasos:  
  
1.  Asegúrese de que el número de instancias activas no aumente.  
  
2.  Asegúrese de que servicio del Agente SQL está en ejecución.  
  
3.  Si está configurado el análisis OLAP, asegúrese de que se ejecute un trabajo BAM_AN a intervalos periódicos.  
  
4.  Asegúrese de que el trabajo BAM_DM (mantenimiento de datos) esté programado para ejecutarse a intervalos periódicos.