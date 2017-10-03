---
title: Optimizar el rendimiento de la base de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a95caf60-f1f5-458f-8a81-0aead88f07be
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe9148c5b14c5c915de9a8d16699856922e051a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-database-performance"></a><span data-ttu-id="ccc4b-102">Optimizar el rendimiento de la base de datos</span><span class="sxs-lookup"><span data-stu-id="ccc4b-102">Optimizing Database Performance</span></span>
<span data-ttu-id="ccc4b-103">BizTalk Server es una aplicación de base de datos consume que requieran la creación de hasta 13 bases de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ccc4b-103">BizTalk Server is an extremely database-intensive application that may require the creation of up to 13 databases in SQL Server.</span></span> <span data-ttu-id="ccc4b-104">Dado que uno de los objetivos principales de diseño de BizTalk Server es garantizar que ningún mensaje se pierdan, BizTalk Server conserva los datos en el disco con gran frecuencia y además, lo hace en el contexto de una transacción MSDTC.</span><span class="sxs-lookup"><span data-stu-id="ccc4b-104">Because one of the primary design goals of BizTalk Server is to ensure that no messages are lost, BizTalk Server persists data to disk with great frequency and furthermore, does so within the context of an MSDTC transaction.</span></span> <span data-ttu-id="ccc4b-105">Por lo tanto, el rendimiento de la base de datos tiene gran importancia para el rendimiento general de cualquier solución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ccc4b-105">Therefore, database performance is paramount to the overall performance of any BizTalk Server solution.</span></span>  
  
 <span data-ttu-id="ccc4b-106">Esta sección describen métodos generales para maximizar el rendimiento de SQL Server, así como métodos para maximizar el rendimiento de la base de datos que son específicos de un entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ccc4b-106">This section describes general methods for maximizing SQL Server performance as well as methods for maximizing database performance that are specific to a BizTalk Server environment.</span></span> <span data-ttu-id="ccc4b-107">Para obtener más información sobre cómo optimizar el rendimiento de la base de datos de BizTalk, consulte la [notas del producto optimización de base de datos de BizTalk](http://go.microsoft.com/fwlink/?LinkId=101578) (http://go.microsoft.com/fwlink/?LinkId=101578).</span><span class="sxs-lookup"><span data-stu-id="ccc4b-107">For additional information about optimizing BizTalk database performance, see the [BizTalk Database Optimization whitepaper](http://go.microsoft.com/fwlink/?LinkId=101578) (http://go.microsoft.com/fwlink/?LinkId=101578).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ccc4b-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ccc4b-108">In This Section</span></span>  
  
-   [<span data-ttu-id="ccc4b-109">Base de datos de configuración previa Optimizations2</span><span class="sxs-lookup"><span data-stu-id="ccc4b-109">Pre-Configuration Database Optimizations2</span></span>](../technical-guides/pre-configuration-database-optimizations2.md)  
  
-   [<span data-ttu-id="ccc4b-110">Configuración posterior a la base de datos Optimizations2</span><span class="sxs-lookup"><span data-stu-id="ccc4b-110">Post-Configuration Database Optimizations2</span></span>](../technical-guides/post-configuration-database-optimizations2.md)  
  
-   [<span data-ttu-id="ccc4b-111">Optimizar los grupos de archivos para el Databases2</span><span class="sxs-lookup"><span data-stu-id="ccc4b-111">Optimizing Filegroups for the Databases2</span></span>](../technical-guides/optimizing-filegroups-for-the-databases2.md)  
  
-   [<span data-ttu-id="ccc4b-112">Script de SQL de grupos de archivos de base de datos de cuadro de mensajes de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ccc4b-112">BizTalk Server MessageBox Database Filegroups SQL Script</span></span>](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)  
  
-   [<span data-ttu-id="ccc4b-113">Supervisión del rendimiento de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ccc4b-113">Monitoring SQL Server Performance</span></span>](../technical-guides/monitoring-sql-server-performance.md)