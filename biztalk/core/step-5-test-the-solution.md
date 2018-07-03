---
title: 'Paso 5: Probar la solución | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5ca5301-2ee4-4024-a90a-396ed681d12a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33a51cda93a1c2cdd6f5a70ebd62bf1d9ce05a7e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020855"
---
# <a name="step-5-test-the-solution"></a><span data-ttu-id="f3f8d-102">Paso 5: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="f3f8d-102">Step 5: Test the Solution</span></span>
<span data-ttu-id="f3f8d-103">Objetivo de esta solución es automatizar el proceso de enviar notificaciones a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cada vez que se cierra una nueva oportunidad en Salesforce estableciendo la etapa de la oportunidad **Closed Won**.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-103">This solution aims at automating the process of sending notifications to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], every time a new opportunity is closed in Salesforce by setting the stage of the opportunity as **Closed Won**.</span></span> <span data-ttu-id="f3f8d-104">Después de recibe la notificación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía una consulta a Salesforce para recuperar los detalles de productos relacionados con la oportunidad y, a continuación, inserta la respuesta de Salesforce en una tabla de base de datos de SQL Server denominada **OrderDetails**.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-104">After the notification is received [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a query to Salesforce to retrieve product details related to the opportunity, and then inserts the response from Salesforce into a SQL Server database table called **OrderDetails**.</span></span> <span data-ttu-id="f3f8d-105">Por lo tanto, para probar esta solución, actualizaremos la etapa de oportunidad **Closed Won** y como resultado, deben insertarse los registros pertinentes en la tabla OrderDetails en la base de datos de pedidos.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-105">So, to test this solution, we will update the stage of an opportunity to **Closed Won** and as a result, relevant records must get inserted in the OrderDetails table in the Orders database.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="f3f8d-106">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="f3f8d-106">To test the solution</span></span>  
  
1. <span data-ttu-id="f3f8d-107">Inicie sesión en `https://login.salesforce.com/?lt=de` con las credenciales de inicio de sesión de desarrollador de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-107">Log in to `https://login.salesforce.com/?lt=de`, using the Salesforce developer login credentials.</span></span>  
  
2. <span data-ttu-id="f3f8d-108">En la barra de navegación, haga clic en **oportunidades**y, a continuación, haga clic en **oportunidad con customer1**.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-108">In the navigation bar, click **Opportunities**, and then click **Opportunity with Customer 1**.</span></span> <span data-ttu-id="f3f8d-109">Se creó esta oportunidad en [paso 2: configurar el sistema Salesforce](../core/step-2-set-up-the-salesforce-system.md).</span><span class="sxs-lookup"><span data-stu-id="f3f8d-109">You had created this opportunity in [Step 2: Set up the Salesforce System](../core/step-2-set-up-the-salesforce-system.md).</span></span>  
  
3. <span data-ttu-id="f3f8d-110">En el **detalle de oportunidad** sección, tome nota de los productos asociados en el **productos (estándar)** sección.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-110">In the **Opportunity Detail** section, take a note of the associated products in the **Products (Standard)** section.</span></span> <span data-ttu-id="f3f8d-111">Los valores que especifique en esta sección se insertarán finalmente en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-111">The values you under this section will finally get inserted into the SQL Server database.</span></span> <span data-ttu-id="f3f8d-112">En el **detalle de oportunidad** sección haga clic en el **editar** botón y cambie el valor de **fase** campo **Closed Won**.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-112">Under the **Opportunity Detail** section click the **Edit** button and change the value of **Stage** field to **Closed Won**.</span></span> <span data-ttu-id="f3f8d-113">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-113">Click **Save**.</span></span>  
  
    <span data-ttu-id="f3f8d-114">![Editar una oportunidad existente](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")</span><span class="sxs-lookup"><span data-stu-id="f3f8d-114">![Edit an existing opportunity](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")</span></span>  
  
4. <span data-ttu-id="f3f8d-115">En SQL Server Management Studio, ejecutar una consulta en el **OrderDetails** tabla para seleccionar todas las filas.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-115">In SQL Server Management Studio, run a query on the **OrderDetails** table to select all rows.</span></span>  
  
    <span data-ttu-id="f3f8d-116">![Salida de la consulta SQL](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")</span><span class="sxs-lookup"><span data-stu-id="f3f8d-116">![SQL Query output](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")</span></span>  
  
    <span data-ttu-id="f3f8d-117">Observe que se muestran los productos enumerados en la oportunidad para la que cambió la etapa.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-117">Notice that it lists the products that are listed in the opportunity for which you changed the stage.</span></span>  
  
    <span data-ttu-id="f3f8d-118">![Agregar productos a una oportunidad](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span><span class="sxs-lookup"><span data-stu-id="f3f8d-118">![Add products to an opportunity](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span></span>  
  
   <span data-ttu-id="f3f8d-119">Puede ver que los registros se escriben en el **OrderDetails** tabla corresponden a las oportunidades de venta creada en Salesforce para un determinado conjunto de productos.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-119">You can see that the records entered in the **OrderDetails** table correspond to the sales opportunity created in Salesforce for a given set of products.</span></span> <span data-ttu-id="f3f8d-120">Puede repetir estos pasos creando nuevas oportunidades y asociando nuevos productos a cada oportunidad.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-120">You can repeat these steps by creating new opportunities and associating new products with the opportunity.</span></span>