---
title: Cómo identificar cuellos de botella en la base de datos BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6814c0df-3ce1-44f8-8e63-af6e23336c6d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8fa54379d6d314993ac33b7d6395f061e48849d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254108"
---
# <a name="how-to-identify-bottlenecks-in-the-bam-database"></a><span data-ttu-id="e25cc-102">Cómo identificar cuellos de botella en la base de datos de BAM</span><span class="sxs-lookup"><span data-stu-id="e25cc-102">How to Identify Bottlenecks in the BAM Database</span></span>
<span data-ttu-id="e25cc-103">Para identificar cuellos de botella en la base de datos de BAM, realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="e25cc-103">To identify bottlenecks in the BAM database, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="e25cc-104">Asegúrese de que el número de instancias activas no aumente.</span><span class="sxs-lookup"><span data-stu-id="e25cc-104">Ensure that the Active Instances count is not climbing.</span></span>  
  
2.  <span data-ttu-id="e25cc-105">Asegúrese de que servicio del Agente SQL está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="e25cc-105">Ensure that the SQL-Agent Service is running.</span></span>  
  
3.  <span data-ttu-id="e25cc-106">Si está configurado el análisis OLAP, asegúrese de que se ejecute un trabajo BAM_AN a intervalos periódicos.</span><span class="sxs-lookup"><span data-stu-id="e25cc-106">If OLAP Analysis is configured ensure that the BAM_AN_ job is running at periodic intervals.</span></span>  
  
4.  <span data-ttu-id="e25cc-107">Asegúrese de que el trabajo BAM_DM (mantenimiento de datos) esté programado para ejecutarse a intervalos periódicos.</span><span class="sxs-lookup"><span data-stu-id="e25cc-107">Ensure that BAM_DM_ (Data Maintenance) job is scheduled to run at periodic intervals.</span></span>