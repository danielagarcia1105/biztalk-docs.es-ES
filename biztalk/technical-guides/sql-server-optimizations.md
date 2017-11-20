---
title: Optimizaciones de SQL Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb735b54-595e-4dd0-9e4d-9a5e7a007a78
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3783c09b1155202ac8fe5a964d16c24d33082c26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sql-server-optimizations"></a><span data-ttu-id="c78e4-102">Optimizaciones de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c78e4-102">SQL Server Optimizations</span></span>
<span data-ttu-id="c78e4-103">BizTalk Server es una muy base de datos intensivas aplicación que requieran la creación de hasta 13 bases de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c78e4-103">BizTalk Server is an extremely database intensive application that may require the creation of up to 13 databases in SQL Server.</span></span> <span data-ttu-id="c78e4-104">Dado que uno de los objetivos principales de diseño de BizTalk Server es garantizar que ningún mensaje se pierdan, BizTalk Server conserva los datos en el disco con gran frecuencia y además, lo hace en el contexto de una transacción MSDTC.</span><span class="sxs-lookup"><span data-stu-id="c78e4-104">Because one of the primary design goals of BizTalk Server is to ensure that no messages are lost, BizTalk Server persists data to disk with great frequency and furthermore, does so within the context of an MSDTC transaction.</span></span> <span data-ttu-id="c78e4-105">Por lo tanto, el rendimiento de la base de datos tiene gran importancia para el rendimiento general de cualquier solución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c78e4-105">Therefore, database performance is paramount to the overall performance of any BizTalk Server solution.</span></span>  
  
 <span data-ttu-id="c78e4-106">Esta sección describen métodos generales para maximizar el rendimiento de SQL Server, así como métodos para maximizar el rendimiento de la base de datos que son específicos de un entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c78e4-106">This section describes general methods for maximizing SQL Server performance as well as methods for maximizing database performance that are specific to a BizTalk Server environment.</span></span> <span data-ttu-id="c78e4-107">Para obtener información adicional acerca de cómo optimizar BizTalk rendimiento de base de datos, vea el artículo de TechNet de optimización de base de datos de BizTalk en [http://go.microsoft.com/fwlink/?LinkId=118001](http://go.microsoft.com/fwlink/?LinkId=118001).</span><span class="sxs-lookup"><span data-stu-id="c78e4-107">For additional information on optimizing BizTalk database performance, see the BizTalk Database Optimization TechNet article at [http://go.microsoft.com/fwlink/?LinkId=118001](http://go.microsoft.com/fwlink/?LinkId=118001).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c78e4-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c78e4-108">In This Section</span></span>  
  
-   [<span data-ttu-id="c78e4-109">Base de datos de configuración previa Optimizations1</span><span class="sxs-lookup"><span data-stu-id="c78e4-109">Pre-Configuration Database Optimizations1</span></span>](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="c78e4-110">Configuración posterior a la base de datos Optimizations1</span><span class="sxs-lookup"><span data-stu-id="c78e4-110">Post-Configuration Database Optimizations1</span></span>](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="c78e4-111">Optimizar los grupos de archivos para el Databases1</span><span class="sxs-lookup"><span data-stu-id="c78e4-111">Optimizing Filegroups for the Databases1</span></span>](../technical-guides/optimizing-filegroups-for-the-databases1.md)