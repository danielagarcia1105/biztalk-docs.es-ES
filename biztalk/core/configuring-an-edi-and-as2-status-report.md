---
title: Configurar un informe de estado de AS2 y EDI | Documentos de Microsoft
description: Crear EDI o expresión de consulta de informes de estado de AS2 y seleccione los datos que desea mostrar en el informe para el servidor BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6490864d-f1e6-4932-aefb-c332a595aad7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 833e3c6c26cdac57d7cc57d828b66a66b9eb37f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233684"
---
# <a name="configure-an-edi-and-as2-status-report"></a><span data-ttu-id="440c6-103">Configurar un informe de estado de AS2 y EDI</span><span class="sxs-lookup"><span data-stu-id="440c6-103">Configure an EDI and AS2 Status Report</span></span>
<span data-ttu-id="440c6-104">Después de que se ha habilitado EDI o informes de estado de AS2, muestre el informe de estado que desee desde la **informes de estado de EDI** o **informes de estado de EDIINT** sección de la **concentrador de grupo** pestaña de la **información general del grupo** página en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="440c6-104">After you have enabled EDI or AS2 status reports, you display the status report you want from the **EDI Status Reports** or **EDIINT Status Reports** section of the **Group Hub** tab of the **Group Overview** page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="440c6-105">Al mostrar un informe de estado, verá un conjunto de datos predeterminado.</span><span class="sxs-lookup"><span data-stu-id="440c6-105">When you display a status report, you will see a default set of data.</span></span> <span data-ttu-id="440c6-106">Puede configurar los siguientes aspectos de los informes de estado:</span><span class="sxs-lookup"><span data-stu-id="440c6-106">You can configure the following aspects of the status reports:</span></span>  
  
-   <span data-ttu-id="440c6-107">La expresión de la consulta que se ejecuta para determinar el intervalo de datos que notifica el estado, por ejemplo, el rango de fechas, la dirección de los datos (recibidos o enviados) o el valor del estado (Aceptado, Rechazado, Todo, etc.)</span><span class="sxs-lookup"><span data-stu-id="440c6-107">The query expression that is run to determine the range of data that status is reported for, for example, the date range, the direction of the data (receive or send), or the status value (Accepted, Rejected, All, etc.)</span></span>  
  
-   <span data-ttu-id="440c6-108">El tipo de datos que aparece en el panel de informe de estado, como determina las columnas de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="440c6-108">The type of data displayed in the status report pane, as determined by the data columns in the report.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="440c6-109">Siempre que el informe de estado esté habilitado, todos los estados se guardarán en su ubicación.</span><span class="sxs-lookup"><span data-stu-id="440c6-109">Whenever status reporting is enabled, all status will be saved in storage.</span></span> <span data-ttu-id="440c6-110">Mediante la personalización de la expresión de consulta o columnas de estado, se definen los datos guardados que se visualizan.</span><span class="sxs-lookup"><span data-stu-id="440c6-110">By customizing the query expression or status columns, you are defining which saved data is displayed.</span></span>  
  
 <span data-ttu-id="440c6-111">Existen cinco informes de estado diferentes EDI y AS2 (vea [tipos de informes de EDI y AS2 estado](../core/types-of-edi-and-as2-status-reports.md)).</span><span class="sxs-lookup"><span data-stu-id="440c6-111">Five different EDI and AS2 status reports are available (see [Types of EDI and AS2 Status Reports](../core/types-of-edi-and-as2-status-reports.md)).</span></span> <span data-ttu-id="440c6-112">El modo de configuración de los informes es el mismo, aunque los datos de los informes sean distinto.</span><span class="sxs-lookup"><span data-stu-id="440c6-112">The way that you configure each report is the same, even though the data for each report is different.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="440c6-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="440c6-113">Prerequisites</span></span>  
 <span data-ttu-id="440c6-114">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="440c6-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="configure-the-status-report-query-expression"></a><span data-ttu-id="440c6-115">Configurar la expresión de consulta de informe de estado</span><span class="sxs-lookup"><span data-stu-id="440c6-115">Configure the status report query expression</span></span>  
  
1.  <span data-ttu-id="440c6-116">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **grupo de BizTalk** nodo para ver el **información general del grupo** panel.</span><span class="sxs-lookup"><span data-stu-id="440c6-116">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **BizTalk Group** node to see the **Group Overview** pane.</span></span>  
  
2.  <span data-ttu-id="440c6-117">En la parte inferior de la **concentrador de grupo** pestaña en el **información general del grupo** panel, haga clic en el informe de estado que desea configurar, como **intercambio EDI y estado de confirmación correlacionado**.</span><span class="sxs-lookup"><span data-stu-id="440c6-117">At the bottom of the **Group Hub** tab in the **Group Overview** pane, click the status report that you want to configure, such as **EDI Interchange and Correlated ACK Status**.</span></span>  
  
3.  <span data-ttu-id="440c6-118">En el **expresión de consulta** área del panel de informe de estado, compruebe que todos los criterios de filtro que desea definir para la consulta están presentes.</span><span class="sxs-lookup"><span data-stu-id="440c6-118">In the **Query Expression** area of the status report pane, verify that all filter criteria that you want to define for the query are present.</span></span> <span data-ttu-id="440c6-119">Si no es así, haga clic en la flecha hacia abajo en la fila vacía de la **nombre de campo** columna en la parte inferior de la expresión de consulta y seleccione los criterios que desea agregar a la expresión de consulta de filtro.</span><span class="sxs-lookup"><span data-stu-id="440c6-119">If not, click the down arrow in the empty row in the **Field Name** column at the bottom of the query expression, and select any filter criteria that you want to add to the query expression.</span></span> <span data-ttu-id="440c6-120">Puede eliminar una fila de criterios de filtro, seleccione la fila y haga clic en el **eliminar** botón en el teclado.</span><span class="sxs-lookup"><span data-stu-id="440c6-120">You can delete a filter criteria row by selecting the row and clicking the **Delete** button on the keyboard.</span></span>  
  
4.  <span data-ttu-id="440c6-121">Compruebe que los valores de las expresiones de filtro son los deseados.</span><span class="sxs-lookup"><span data-stu-id="440c6-121">Verify that the values for the filter expressions are as desired.</span></span> <span data-ttu-id="440c6-122">Si no es así, haga clic en la flecha abajo de la **operador** columna para seleccionar una operación de consulta y especifique el valor adecuado en el **valor** columna.</span><span class="sxs-lookup"><span data-stu-id="440c6-122">If not, click the down arrow for the **Operator** column to select a query operation, and enter the appropriate value in the **Value** column.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="440c6-123">Los operadores y valores disponibles para los criterios de filtro en las expresiones de consulta se describen en [tipos de informes de EDI y AS2 estado](../core/types-of-edi-and-as2-status-reports.md) y **interfaz de usuario de informes de estado de EDI y AS2** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="440c6-123">The operators and values available for filter criteria in the query expressions are described in [Types of EDI and AS2 Status Reports](../core/types-of-edi-and-as2-status-reports.md) and the **EDI-AS2 Status Reports UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
5.  <span data-ttu-id="440c6-124">Para ejecutar la consulta que muestra el informe de estado según los criterios de filtro, haga clic en **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="440c6-124">To run the query, displaying the status report according to the filter criteria, click **Run Query**.</span></span>  
  
6.  <span data-ttu-id="440c6-125">Para guardar una expresión de consulta como archivo .btq, haga clic en **Guardar como**, especifique la carpeta y escriba un nombre de archivo y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="440c6-125">To save a query expression as a .btq file, click **Save As**, specify the folder and enter a filename, and then click **Save**.</span></span>  
  
7.  <span data-ttu-id="440c6-126">Para abrir un archivo guardado como .btq, haga clic en **Abrir consulta**.</span><span class="sxs-lookup"><span data-stu-id="440c6-126">To open a saved .btq file, click **Open Query**.</span></span>  
  
## <a name="configure-the-type-of-data-displayed-in-the-status-report-pane"></a><span data-ttu-id="440c6-127">Configurar el tipo de datos que se muestran en el panel de informe de estado</span><span class="sxs-lookup"><span data-stu-id="440c6-127">Configure the type of data displayed in the status report pane</span></span>  
  
1.  <span data-ttu-id="440c6-128">Haga clic en el área de resultados del panel de informe de estado y, a continuación, haga clic en **agregar o quitar columnas**.</span><span class="sxs-lookup"><span data-stu-id="440c6-128">Right-click the status results area of the status report pane, and then click **Add/Remove Columns**.</span></span>  
  
2.  <span data-ttu-id="440c6-129">Para agregar una categoría de estado a la lista de columnas mostradas, haga clic en una columna en la **columnas disponibles** lista y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="440c6-129">To add a status category to the displayed columns list, click a column in the **Available columns** list, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="440c6-130">Para quitar una categoría de estado de la lista de columnas mostradas, haga clic en una columna en la **columnas mostradas** lista y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="440c6-130">To remove a status category from the displayed columns list, click a column in the **Displayed columns** list, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="440c6-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="440c6-131">See Also</span></span>  
 <span data-ttu-id="440c6-132">[Supervisión de soluciones EDI y AS2](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="440c6-132">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="440c6-133">[EDI y AS2 informes de estado](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="440c6-133">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 <span data-ttu-id="440c6-134">[Habilitar informes de estado de AS2 y EDI](../core/enabling-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="440c6-134">[Enabling EDI and AS2 Status Reports](../core/enabling-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="440c6-135">Mostrar un EDI o informes de estado de AS2</span><span class="sxs-lookup"><span data-stu-id="440c6-135">Displaying an EDI or AS2 Status Report</span></span>](../core/displaying-an-edi-or-as2-status-report.md)