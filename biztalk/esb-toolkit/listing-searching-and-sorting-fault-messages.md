---
title: Enumerar, buscar y ordenar los mensajes de error | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 850b9682-8eba-4a3f-8508-d3eefcd715b7
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 768dd7f51ff09bad76115f8a7e2a95a11ce47981
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294644"
---
# <a name="listing-searching-and-sorting-fault-messages"></a><span data-ttu-id="c204c-102">Enumerar, buscar y ordenar los mensajes de error</span><span class="sxs-lookup"><span data-stu-id="c204c-102">Listing, Searching, and Sorting Fault Messages</span></span>
<span data-ttu-id="c204c-103">Puede usar la página de inicio del Portal de administración de ESB para obtener una vista general del estado de las aplicaciones que se ejecutan en Microsoft BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c204c-103">You can use the Home page of the ESB Management Portal to obtain an overall view of the status of the applications executing within Microsoft BizTalk Server.</span></span> <span data-ttu-id="c204c-104">La página de errores se puede usar para consultar los mensajes de error, en función de un intervalo de criterios.</span><span class="sxs-lookup"><span data-stu-id="c204c-104">The Faults page can be used to query for fault messages, based on a range of criteria.</span></span>  
  
### <a name="to-see-an-overview-of-the-status-of-current-biztalk-server-applications"></a><span data-ttu-id="c204c-105">Para ver una descripción general del estado de las aplicaciones actuales de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c204c-105">To see an overview of the status of current BizTalk Server applications</span></span>  
  
1.  <span data-ttu-id="c204c-106">Abra la [página principal del Portal](../esb-toolkit/portal-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="c204c-106">Open the [Portal Home Page](../esb-toolkit/portal-home-page.md).</span></span> <span data-ttu-id="c204c-107">Esta página muestra el estado general de la aplicación, un resumen de errores, solicitudes recientes para el registro de Universal Description, Discovery y Integration (UDDI) y gráficos que muestren un desglose de errores por tipo y por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c204c-107">This page displays the overall application state, a summary of faults, recent requests for Universal Description, Discovery, and Integration (UDDI) registration, and charts that show a breakdown of faults by type and by application.</span></span>  
  
2.  <span data-ttu-id="c204c-108">Para seleccionar las aplicaciones para el que desea ver la información, haga clic en el **seleccionar aplicaciones** vincular por encima del primer gráfico y, a continuación, active o desactive las casillas de verificación en la lista de aplicaciones instaladas de BizTalk Server que aparece.</span><span class="sxs-lookup"><span data-stu-id="c204c-108">To select the applications for which you want to view information, click the **Select Applications** link above the first chart, and then select or clear the check boxes in the list of installed BizTalk Server applications that appears.</span></span>  
  
3.  <span data-ttu-id="c204c-109">Para cambiar el período para el que el portal muestra información, seleccione **hora, día, semana, mes, trimestre, año,** o **todos los** en la lista desplegable situada encima del primer gráfico.</span><span class="sxs-lookup"><span data-stu-id="c204c-109">To change the period for which the portal displays information, select **Hour, Day, Week, Month, Quarter, Year,** or **ALL** in the drop-down list above the first chart.</span></span>  
  
4.  <span data-ttu-id="c204c-110">Para cambiar la configuración predeterminada utilizada en la página principal de la lista de aplicaciones y el período de presentación, modifique la configuración en el [página de configuración de Portal de mi](../esb-toolkit/portal-my-settings-page.md).</span><span class="sxs-lookup"><span data-stu-id="c204c-110">To change the default settings used on the Home page for the list of applications and the display period, edit the settings on the [Portal My Settings Page](../esb-toolkit/portal-my-settings-page.md).</span></span>  
  
### <a name="to-list-search-for-and-sort-fault-messages-in-the-esb-management-portal"></a><span data-ttu-id="c204c-111">Para obtener una lista, buscar y ordenar los mensajes en el Portal de administración de ESB de error</span><span class="sxs-lookup"><span data-stu-id="c204c-111">To list, search for, and sort fault messages in the ESB Management Portal</span></span>  
  
1.  <span data-ttu-id="c204c-112">Abra la [página Configuración de error](../esb-toolkit/fault-settings-page.md).</span><span class="sxs-lookup"><span data-stu-id="c204c-112">Open the [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span> <span data-ttu-id="c204c-113">Esta página muestra una lista de propiedades para cada error truncada y admite el análisis de errores de una gama de criterios.</span><span class="sxs-lookup"><span data-stu-id="c204c-113">This page displays a truncated list of properties for each fault and supports analysis of faults by a range of criteria.</span></span>  
  
2.  <span data-ttu-id="c204c-114">Para filtrar la lista de errores que se muestra en la página, use las listas desplegables y cuadros de texto situado encima de la lista de errores.</span><span class="sxs-lookup"><span data-stu-id="c204c-114">To filter the list of faults displayed on the page, use the drop-down lists and text boxes above the list of faults.</span></span> <span data-ttu-id="c204c-115">Puede filtrar las filas mostradas por aplicación, período, número de código de error, nombre de la categoría de error, el texto del tipo de error y gravedad de error mínimo o máximo.</span><span class="sxs-lookup"><span data-stu-id="c204c-115">You can filter the rows displayed by application, period, fault code number, fault category name, error type text, and minimum/maximum fault severity.</span></span> <span data-ttu-id="c204c-116">Deje cualquiera de los controles en blanco para recuperar todos los mensajes independientemente de su valor para este criterio.</span><span class="sxs-lookup"><span data-stu-id="c204c-116">Leave any of the controls empty to retrieve all messages irrespective of their value for this criterion.</span></span>  
  
3.  <span data-ttu-id="c204c-117">Haga clic en **aplicar filtros** para ver la lista de errores de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="c204c-117">Click **Apply Filters** to see the list of matching faults.</span></span> <span data-ttu-id="c204c-118">Tenga en cuenta que el filtrado en las bases de datos de errores muy grandes puede tardar unos segundos para mostrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="c204c-118">Note that filtering on very large fault databases may take a few seconds to display results.</span></span>  
  
4.  <span data-ttu-id="c204c-119">Para mostrar más o menos filas en la página, seleccione el valor adecuado en el **registros por página** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c204c-119">To display more or fewer rows in the page, select the appropriate value in the **Records Per Page** drop-down list.</span></span>  
  
5.  <span data-ttu-id="c204c-120">Para ordenar la lista de mensajes de error, haga clic en un encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="c204c-120">To sort the list of fault messages, click a column heading.</span></span> <span data-ttu-id="c204c-121">Para ordenar las filas en orden inverso, haga clic en la misma columna de encabezado de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c204c-121">To sort the rows in reverse order, click the same column heading again.</span></span>  
  
6.  <span data-ttu-id="c204c-122">Haga clic en **exportar a Excel** para descargar la lista completa de los mensajes de error en un formato que se puede ver en Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="c204c-122">Click **Export To Excel** to download the complete list of fault messages in a format that you can view in Microsoft Excel.</span></span>