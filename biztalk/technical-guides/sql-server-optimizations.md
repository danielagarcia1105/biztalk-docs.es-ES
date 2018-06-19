---
title: Optimizaciones de SQL Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb735b54-595e-4dd0-9e4d-9a5e7a007a78
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36317d99387fde1d7b5e1c56b45255129daedb25
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710807"
---
# <a name="sql-server-optimizations"></a><span data-ttu-id="a229d-102">Optimizaciones de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a229d-102">SQL Server Optimizations</span></span>
<span data-ttu-id="a229d-103">BizTalk Server es una muy base de datos intensivas aplicación que requieran la creación de hasta 13 bases de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a229d-103">BizTalk Server is an extremely database intensive application that may require the creation of up to 13 databases in SQL Server.</span></span> <span data-ttu-id="a229d-104">Dado que uno de los objetivos principales de diseño de BizTalk Server es garantizar que ningún mensaje se pierdan, BizTalk Server conserva los datos en el disco con gran frecuencia y además, lo hace en el contexto de una transacción MSDTC.</span><span class="sxs-lookup"><span data-stu-id="a229d-104">Because one of the primary design goals of BizTalk Server is to ensure that no messages are lost, BizTalk Server persists data to disk with great frequency and furthermore, does so within the context of an MSDTC transaction.</span></span> <span data-ttu-id="a229d-105">Por lo tanto, el rendimiento de la base de datos tiene gran importancia para el rendimiento general de cualquier solución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a229d-105">Therefore, database performance is paramount to the overall performance of any BizTalk Server solution.</span></span>  
  
<span data-ttu-id="a229d-106">Esta sección describen métodos generales para maximizar el rendimiento de SQL Server, así como métodos para maximizar el rendimiento de la base de datos que son específicos de un entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a229d-106">This section describes general methods for maximizing SQL Server performance as well as methods for maximizing database performance that are specific to a BizTalk Server environment.</span></span> <span data-ttu-id="a229d-107">Los vínculos siguientes también son buenos recursos:</span><span class="sxs-lookup"><span data-stu-id="a229d-107">The following links are also good resources:</span></span> 

- [<span data-ttu-id="a229d-108">El servidor BizTalk Server: Recomendaciones para instalar, ajustar el tamaño, implementar y mantener una solución</span><span class="sxs-lookup"><span data-stu-id="a229d-108">BizTalk Server: Recommendations for Installing, Sizing, Deploying, and Maintaining a Solution</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/666.biztalk-server-recommendations-for-installing-sizing-deploying-and-maintaining-a-solution.aspx)

- [<span data-ttu-id="a229d-109">Guía de optimización del rendimiento de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a229d-109">BizTalk Server Performance Optimization Guide</span></span>](biztalk-server-2013-performance-optimization-guide.md)

  
## <a name="next-steps"></a><span data-ttu-id="a229d-110">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a229d-110">Next steps</span></span>
  
-   [<span data-ttu-id="a229d-111">Optimizaciones de base de datos previas a la configuración</span><span class="sxs-lookup"><span data-stu-id="a229d-111">Pre-Configuration Database Optimizations</span></span>](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="a229d-112">Optimizaciones de base de datos después de la configuración</span><span class="sxs-lookup"><span data-stu-id="a229d-112">Post-Configuration Database Optimizations</span></span>](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="a229d-113">Optimización de grupos de archivos para las bases de datos</span><span class="sxs-lookup"><span data-stu-id="a229d-113">Optimizing Filegroups for the Databases</span></span>](../technical-guides/optimizing-filegroups-for-the-databases1.md)