---
title: "Cómo utilizar una base de datos como un origen de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Business Rule Composer, data sources
ms.assetid: a68057ed-836f-499f-bb80-f644d81bcfc5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3a9201ee729288a819a3d527a6ecb4fefd32797
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-a-database-as-a-data-source"></a><span data-ttu-id="34a40-102">Cómo utilizar una base de datos como origen de datos</span><span class="sxs-lookup"><span data-stu-id="34a40-102">How to Use a Database as a Data Source</span></span>
<span data-ttu-id="34a40-103">Puede especificar una base de datos como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="34a40-103">You can specify a database as a data source.</span></span> <span data-ttu-id="34a40-104">A continuación, puede seleccionar una tabla o columna de tabla de la base de datos y arrastrarla hasta una definición de vocabulario o regla para utilizarla como un hecho.</span><span class="sxs-lookup"><span data-stu-id="34a40-104">You can subsequently select a table or table column from the database, and drag it onto a vocabulary definition or rule to use as a fact.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34a40-105">Puede enlazar a la fila o tabla base de datos mediante **DataConnection** o **TypedDataTable** seleccionando "Conexión de datos" o "Tabla o fila de la base de datos" de la **tipo de enlace de la base de datos**  cuadro de lista desplegable en la ventana de propiedades para el **bases de datos** ficha del explorador de hechos.</span><span class="sxs-lookup"><span data-stu-id="34a40-105">You can choose to bind to the database row/table using either **DataConnection** or **TypedDataTable** by selecting "Data connection" or "Database table/row" from the **Database binding type** drop-down box in the Property Window for the **Databases** tab of Fact Explorer.</span></span> <span data-ttu-id="34a40-106">**DataConnection** enlace se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="34a40-106">**DataConnection** binding is used by default.</span></span>  
  
### <a name="to-specify-a-sql-database-as-a-data-source"></a><span data-ttu-id="34a40-107">Para especificar una base de datos SQL como origen de datos</span><span class="sxs-lookup"><span data-stu-id="34a40-107">To specify a SQL database as a data source</span></span>  
  
1.  <span data-ttu-id="34a40-108">En la ventana Explorador de hechos, haga clic en el **bases de datos** ficha.</span><span class="sxs-lookup"><span data-stu-id="34a40-108">In the Facts Explorer window, click the **Databases** tab.</span></span>  
  
2.  <span data-ttu-id="34a40-109">Haga clic en el **servidores** nodo y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="34a40-109">Right-click the **Servers** node, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="34a40-110">Seleccione en la lista desplegable un servidor de base de datos disponible.</span><span class="sxs-lookup"><span data-stu-id="34a40-110">In the drop-down list, select an available database server.</span></span>  
  
4.  <span data-ttu-id="34a40-111">Seleccione un tipo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="34a40-111">Select an authentication type.</span></span> <span data-ttu-id="34a40-112">Si selecciona autenticación de SQL, escriba un nombre de inicio de sesión y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="34a40-112">If you select SQL authentication, enter a logon name and password.</span></span> <span data-ttu-id="34a40-113">Cuando haya introducido su información de autenticación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="34a40-113">When you have entered your authentication information, click **OK**.</span></span>  
  
     <span data-ttu-id="34a40-114">![Captura de pantalla de bases de datos del explorador de árbol. ] (../core/media/ebiz-dbbrows.gif "ebiz_dbbrows")</span><span class="sxs-lookup"><span data-stu-id="34a40-114">![Screenshot of databases of tree brower.](../core/media/ebiz-dbbrows.gif "ebiz_dbbrows")</span></span>  
<span data-ttu-id="34a40-115">Examinar una base de datos</span><span class="sxs-lookup"><span data-stu-id="34a40-115">Browsing a database</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34a40-116">No se admiten vistas de la base de datos del servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34a40-116">SQL Server database views are not supported.</span></span>