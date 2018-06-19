---
title: Cómo determinar y establecer Roles de sistema de escritura de eventos para las actividades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73bfe8ff-167a-4bf0-ab87-3926290d52d8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc9fa663d395fc36205e137da374f17cb9470521
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249868"
---
# <a name="how-to-determine-and-set-event-writer-roles-for-activities"></a><span data-ttu-id="2ed46-102">Cómo determinar y establecer roles de escritor de eventos para las actividades</span><span class="sxs-lookup"><span data-stu-id="2ed46-102">How to Determine and Set Event Writer Roles for Activities</span></span>
<span data-ttu-id="2ed46-103">BAM proporciona dos modos de seguridad cuando se escriben eventos sobre actividades.</span><span class="sxs-lookup"><span data-stu-id="2ed46-103">BAM provides two modes of security when writing events on activities.</span></span> <span data-ttu-id="2ed46-104">Puede conceder permisos para escribir eventos sobre actividades individuales o conceder permisos para escribir eventos sobre todas las actividades implementadas.</span><span class="sxs-lookup"><span data-stu-id="2ed46-104">You can grant permissions to write events on individual activities or you can grant permissions to write events on all deployed activities.</span></span>  
  
 <span data-ttu-id="2ed46-105">Las funciones de escritor de eventos de actividad que se crean al implementar la definición de BAM proporcionan seguridad de nivel de actividad.</span><span class="sxs-lookup"><span data-stu-id="2ed46-105">Activity-level security is provided by activity event writer roles that are created when you deploy a BAM definition.</span></span> <span data-ttu-id="2ed46-106">Por ejemplo, si implementa una definición para una actividad denominada CreditCard, BAM crea una función de escritor de eventos denominada bam_CreditCard_EventWriter.</span><span class="sxs-lookup"><span data-stu-id="2ed46-106">For example, if you deploy a definition for an activity named CreditCard, BAM creates an event writer role named bam_CreditCard_EventWriter.</span></span> <span data-ttu-id="2ed46-107">Esta función tiene permisos para escribir eventos para la actividad.</span><span class="sxs-lookup"><span data-stu-id="2ed46-107">This role has permissions to write events for the activity.</span></span> <span data-ttu-id="2ed46-108">Para conceder permisos de usuario para escribir eventos para la actividad, agregue el usuario a la función.</span><span class="sxs-lookup"><span data-stu-id="2ed46-108">To grant a user permissions to write events for the activity, you add the user to the role.</span></span>  
  
 <span data-ttu-id="2ed46-109">Como alternativa, puede conceder derechos a los usuarios para escribir eventos en todas las actividades si los agrega al super rol BAM_EVENT_WRITER, que tiene permisos para escribir en todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="2ed46-109">Alternatively, you can grant users rights to write eve2nts to all activities by adding them to the super role BAM_EVENT_WRITER, which has permissions to write to all activities.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2ed46-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2ed46-110">Prerequisites</span></span>  
 <span data-ttu-id="2ed46-111">Para realizar este procedimiento, debe contar con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ed46-111">To perform this procedure, you must have the following:</span></span>  
  
-   <span data-ttu-id="2ed46-112">Una conexión a BAMPrimaryImportDb, donde se implementó la actividad.</span><span class="sxs-lookup"><span data-stu-id="2ed46-112">A connection to BAMPrimaryImportDb on which the activity is deployed.</span></span>  
  
-   <span data-ttu-id="2ed46-113">Permisos DBO en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2ed46-113">DBO permissions on the database.</span></span>  
  
### <a name="to-add-a-user-to-an-event-writer-role"></a><span data-ttu-id="2ed46-114">Para agregar un usuario a una función de escritor de eventos</span><span class="sxs-lookup"><span data-stu-id="2ed46-114">To add a user to an event writer role</span></span>  
  
1.  <span data-ttu-id="2ed46-115">Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **Microsoft SQL Server 2008**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="2ed46-115">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="2ed46-116">En el **conectar con SQL Server** cuadro de diálogo, seleccione el servidor SQL Server y el método de autenticación adecuado y, a continuación, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="2ed46-116">In the **Connect to SQL Server** dialog box, select the SQL Server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="2ed46-117">En el **Explorador de objetos** panel expanda **bases de datos**y, a continuación, seleccione la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="2ed46-117">In the **Object Explorer** pane expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="2ed46-118">Haga clic en el **nueva consulta** icono en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="2ed46-118">Click the **New Query** icon on the toolbar.</span></span>  
  
5.  <span data-ttu-id="2ed46-119">Copie los siguientes comandos y péguelos en la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="2ed46-119">Copy the following commands and paste them into the Query Window.</span></span> <span data-ttu-id="2ed46-120">Reemplace el nombre de dominio, el nombre de usuario y los marcadores de posición del nombre de la actividad con los valores adecuados.</span><span class="sxs-lookup"><span data-stu-id="2ed46-120">Replace the domain name, user name, and activity name placeholders with the appropriate values.</span></span>  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'bam_<activity name>_EventWriter', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="2ed46-121">Los nombres de función distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="2ed46-121">Role names are case-sensitive.</span></span> <span data-ttu-id="2ed46-122">Los nombres de actividad también distinguen entre mayúsculas y minúsculas; es decir, deben coincidir con el uso de mayúsculas y minúsculas utilizado cuando se implementó la actividad.</span><span class="sxs-lookup"><span data-stu-id="2ed46-122">Activity names are also case-sensitive, that is, they must match the case used when deploying the activity.</span></span>  
  
6.  <span data-ttu-id="2ed46-123">Haga clic en el **Execute** icono en la barra de herramientas o presione F5 para ejecutar los comandos.</span><span class="sxs-lookup"><span data-stu-id="2ed46-123">Click the **Execute** icon on the toolbar or press F5 to run the commands.</span></span>  
  
### <a name="to-add-a-user-to-an-event-writer-super-role"></a><span data-ttu-id="2ed46-124">Para agregar un usuario a una superfunción de escritor de eventos</span><span class="sxs-lookup"><span data-stu-id="2ed46-124">To add a user to an event writer super role</span></span>  
  
1.  <span data-ttu-id="2ed46-125">Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **Microsoft SQL Server 2008**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="2ed46-125">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="2ed46-126">En el **conectar con SQL Server** cuadro de diálogo, seleccione el servidor SQL Server y el método de autenticación adecuado y, a continuación, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="2ed46-126">In the **Connect to SQL Server** dialog box, select the SQL Server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="2ed46-127">En el **Explorador de objetos** panel expanda **bases de datos**y, a continuación, seleccione la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="2ed46-127">In the **Object Explorer** pane expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="2ed46-128">Haga clic en el **nueva consulta** icono en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="2ed46-128">Click the **New Query** icon on the toolbar.</span></span>  
  
5.  <span data-ttu-id="2ed46-129">Copie los siguientes comandos y péguelos en la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="2ed46-129">Copy the following commands and paste them into the Query Window.</span></span> <span data-ttu-id="2ed46-130">Reemplace el nombre de dominio y el nombre de usuario con los valores adecuados.</span><span class="sxs-lookup"><span data-stu-id="2ed46-130">Replace the domain name and user name with the appropriate values.</span></span>  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'BAM_EVENT_WRITER', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="2ed46-131">Los nombres de función distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="2ed46-131">Role names are case sensitive.</span></span> <span data-ttu-id="2ed46-132">Debe especificar la función de escritor de evento de acuerdo con lo especificado.</span><span class="sxs-lookup"><span data-stu-id="2ed46-132">You must specify the event writer role as specified.</span></span>  
  
6.  <span data-ttu-id="2ed46-133">Haga clic en el **Execute** icono en la barra de herramientas o presione F5 para ejecutar los comandos.</span><span class="sxs-lookup"><span data-stu-id="2ed46-133">Click the **Execute** icon on the toolbar or press F5 to run the commands.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed46-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ed46-134">See Also</span></span>  
 [<span data-ttu-id="2ed46-135">Administrar la seguridad BAM</span><span class="sxs-lookup"><span data-stu-id="2ed46-135">Managing BAM Security</span></span>](../core/managing-bam-security.md)