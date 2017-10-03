---
title: "Agregar página alerta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0023ee8d-a0d1-4257-95c6-38c95060bd62
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa93a777481c905dbedfffe5e7675335c4aec40b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="add-alert-page"></a><span data-ttu-id="a6fea-102">Agregar página alerta</span><span class="sxs-lookup"><span data-stu-id="a6fea-102">Add Alert Page</span></span>
<span data-ttu-id="a6fea-103">La figura 1 muestra la página Agregar alerta, donde puede crear una nueva alerta, se producirá el portal cuando llega un mensaje de error que cumpla los criterios (condiciones) especificados en la alerta en el portal.</span><span class="sxs-lookup"><span data-stu-id="a6fea-103">Figure 1 shows the Add Alert page, where you can create a new alert that the portal will raise when a fault message matching the criteria (conditions) specified in the alert arrives at the portal.</span></span>  
  
 <span data-ttu-id="a6fea-104">![Agregar página alerta](../esb-toolkit/media/ch8-addalertpage.gif "Ch8-AddAlertPage")</span><span class="sxs-lookup"><span data-stu-id="a6fea-104">![Add Alert Page](../esb-toolkit/media/ch8-addalertpage.gif "Ch8-AddAlertPage")</span></span>  
  
 <span data-ttu-id="a6fea-105">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="a6fea-105">**Figure 1**</span></span>  
  
 <span data-ttu-id="a6fea-106">**La página de ESB Management Portal Agregar alerta**</span><span class="sxs-lookup"><span data-stu-id="a6fea-106">**The ESB Management Portal Add Alert page**</span></span>  
  
 <span data-ttu-id="a6fea-107">En la página Agregar alerta, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6fea-107">On the Add Alert page, you can do the following:</span></span>  
  
-   <span data-ttu-id="a6fea-108">Escriba un nombre para la nueva alerta en el **escriba el nombre de alerta** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="a6fea-108">Type a name for the new alert in the **Enter Alert Name** text box.</span></span>  
  
-   <span data-ttu-id="a6fea-109">Especificar cómo se comparará la alerta a valores de los campos de entrada excepciones en el **agregar condiciones para esta alerta** sección de esta página.</span><span class="sxs-lookup"><span data-stu-id="a6fea-109">Specify how the alert will match to values of the fields in incoming exceptions in the **Add conditions for this alert** section of this page.</span></span> <span data-ttu-id="a6fea-110">Seleccione un campo en el esquema de excepción (como **aplicación, tipo de Error,** o **gravedad de error)** en el **criterios** lista desplegable; seleccione un tipo de comparación para el (por ejemplo, como =, **! =, > =, < =,** o **como**) en el **operador** lista desplegable y escriba o seleccione un valor de la tercera lista.</span><span class="sxs-lookup"><span data-stu-id="a6fea-110">Select a field from the exception schema (such as **Application, Error Type,** or **Fault Severity)** in the **Criteria** drop-down list; select a comparison type for the (such as =, **!=, >=, <=,** or **like**) in the **Operator** drop-down list; and type or select a value from the third list.</span></span> <span data-ttu-id="a6fea-111">Cuando se selecciona un campo de excepción, el **valor** control cambia a un cuadro de texto o una lista desplegable para que escriba o seleccione un valor coincidente.</span><span class="sxs-lookup"><span data-stu-id="a6fea-111">When you select an exception field, the **Value** control changes to either a text box or a drop-down list for you to enter or select a matching value.</span></span>  
  
-   <span data-ttu-id="a6fea-112">Después de seleccionar o escribir los valores de criterios, haga clic en el **agregar** el vínculo para agregar esta condición a la lista en la **condiciones** sección de la página y repetir para agregar cualquier más condiciones que necesite para esta alerta .</span><span class="sxs-lookup"><span data-stu-id="a6fea-112">After selecting or entering the criteria values, click the **Add** link to add this condition to the list in the **Conditions** section of the page, and repeat to add any more conditions you require for this alert.</span></span>  
  
-   <span data-ttu-id="a6fea-113">Haga clic en el **guardar** botón para crear la nueva alerta con el nombre y las condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="a6fea-113">Click the **Save** button to create the new alert with the name and conditions you specified.</span></span>