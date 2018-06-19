---
title: Usar un sistema PeopleSoft | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c228ac23-184f-4c08-922b-ba84f5f2c52f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c93e025ddb2ccec4b0088c20837a4f307f40aada
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287380"
---
# <a name="using-a-peoplesoft-system"></a><span data-ttu-id="c6557-102">Usar un sistema PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="c6557-102">Using a PeopleSoft System</span></span>
<span data-ttu-id="c6557-103">Se puede obtener acceso al sistema PeopleSoft desde un sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el adaptador de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="c6557-103">The PeopleSoft system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the PeopleSoft adapter.</span></span> <span data-ttu-id="c6557-104">Este adaptador pertenece a un grupo de ocho adaptadores de línea empresarial (LOB) que Microsoft distribuye para su uso con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6557-104">This adapter is one of a group of eight line-of-business (LOB) adapters shipped by Microsoft for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c6557-105">El trabajo práctico de PeopleSoft se divide en dos partes.</span><span class="sxs-lookup"><span data-stu-id="c6557-105">The PeopleSoft lab work is divided into two parts.</span></span> <span data-ttu-id="c6557-106">Esta primera práctica (Práctica 1) le permite usar el sistema PeopleSoft sin necesidad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ni de ningún otro producto de Microsoft (salvo quizás Internet Explorer, pero puede usar cualquier explorador).</span><span class="sxs-lookup"><span data-stu-id="c6557-106">This first lab (Lab 1) allows you to use the PeopleSoft system without needing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any Microsoft products (except perhaps Internet Explorer, but you can use any browser).</span></span> <span data-ttu-id="c6557-107">En esta práctica, se conectará al sistema PeopleSoft para localizar y modificar un sencillo registro de datos.</span><span class="sxs-lookup"><span data-stu-id="c6557-107">In this lab, you will connect to the PeopleSoft system to locate and modify a simple data record.</span></span>  
  
 <span data-ttu-id="c6557-108">En la segunda práctica (Práctica 2), creará un proyecto y una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c6557-108">In the second lab (Lab 2), you will create a BizTalk project and orchestration.</span></span> <span data-ttu-id="c6557-109">Después de crear la aplicación, la implementará y usará para conectarse a un sistema PeopleSoft mediante el adaptador de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="c6557-109">After you create the application, you will deploy it and use it to connect to a PeopleSoft system by using the PeopleSoft adapter.</span></span> <span data-ttu-id="c6557-110">El objetivo es obtener acceso a los datos a través de la aplicación BizTalk mediante el adaptador.</span><span class="sxs-lookup"><span data-stu-id="c6557-110">The goal is to access data through the BizTalk application by using the adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c6557-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c6557-111">Prerequisites</span></span>  
 <span data-ttu-id="c6557-112">Para realizar los procedimientos de esta práctica, necesita un explorador y una conexión a Internet, junto con una cuenta de usuario en un sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="c6557-112">To perform the procedures for this lab, you need a browser and an Internet connection, along with a user account on a PeopleSoft system.</span></span> <span data-ttu-id="c6557-113">Debe conocer la ubicación que hay que examinar para obtener acceso web al sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="c6557-113">You need to know the location to browse to for gaining Web access to your PeopleSoft system.</span></span> <span data-ttu-id="c6557-114">NO necesita [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ni ninguna otra tecnología de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6557-114">You do not need [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any other Microsoft technologies.</span></span>  
  
## <a name="lab-1---using-a-peoplesoft-system"></a><span data-ttu-id="c6557-115">Práctica 1: uso de un sistema PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="c6557-115">Lab 1 - Using a PeopleSoft System</span></span>  
 <span data-ttu-id="c6557-116">En esta práctica, usará el sistema PeopleSoft sin emplear ningún componente de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6557-116">In this lab, you will use the PeopleSoft system without using any components of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="c6557-117">El objetivo es probar su conexión con PeopleSoft para garantizar que la segunda práctica funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6557-117">The goal is to test your connectivity to PeopleSoft to ensure that the second lab will work correctly.</span></span> <span data-ttu-id="c6557-118">Inicialmente, se conectará al sistema PeopleSoft a través de su interfaz web, que le permite iniciar sesión a través de un explorador como, por ejemplo, Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c6557-118">Initially you connect to the PeopleSoft system through its Web interface that allows you to log on by using a browser such as Internet Explorer.</span></span>  
  
## <a name="procedures-for-lab-1---using-a-peoplesoft-system"></a><span data-ttu-id="c6557-119">Procedimientos para la Práctica 1: uso de un sistema PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="c6557-119">Procedures for Lab 1 - Using a PeopleSoft System</span></span>  
  
#### <a name="to-log-on-to-peoplesoft-by-using-a-browser"></a><span data-ttu-id="c6557-120">Para iniciar sesión en PeopleSoft a través de un explorador</span><span class="sxs-lookup"><span data-stu-id="c6557-120">To log on to PeopleSoft by using a browser</span></span>  
  
-   <span data-ttu-id="c6557-121">Vaya a una página de inicio de sesión de PeopleSoft para iniciar sesión en el sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="c6557-121">Log on to the PeopleSoft system by browsing to a PeopleSoft logon page.</span></span> <span data-ttu-id="c6557-122">Escriba su **Id. de usuario** y **contraseña** y, a continuación, haga clic en **inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="c6557-122">Enter your **User ID** and **Password** and then click **Sign In**.</span></span>  
  
     ![](../core/media/1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb.gif "1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb")  
  
#### <a name="to-locate-and-modify-peoplesoft-data"></a><span data-ttu-id="c6557-123">Para localizar y modificar datos de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="c6557-123">To locate and modify PeopleSoft data</span></span>  
  
1.  <span data-ttu-id="c6557-124">Si inicia sesión correctamente, obtendrá acceso a la página que permite personalizar el contenido y elegir su diseño.</span><span class="sxs-lookup"><span data-stu-id="c6557-124">A successful logon places you at the page to personalize the content you see by choosing its layout.</span></span> <span data-ttu-id="c6557-125">Desplácese hacia abajo y expanda **establecer Financials/Supply Chain**, haga clic en **definiciones comunes**, haga clic en **ubicación**y, a continuación, haga clic en **ubicación** volver a ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="c6557-125">Scroll down and expand **Set Up Financials/Supply Chain**, click **Common Definitions**, click **Location**, and then click **Location** again.</span></span> <span data-ttu-id="c6557-126">Aparecerá la **ubicación** interfaz de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c6557-126">This brings you to the **Location** search interface.</span></span>  
  
     ![](../core/media/62a89cd4-464c-42fd-91cd-60ceeab5b006.gif "62a89cd4-464c-42fd-91cd-60ceeab5b006")  
  
2.  <span data-ttu-id="c6557-127">Para comenzar la búsqueda, establezca **SetID** a  **=** , establezca **Location Code** a **comienza con**, escriba **un**y, a continuación, haga clic en **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="c6557-127">To begin the search, set **SetID** to **=**, set **Location Code** to **begins with**, enter **A**, and then click **Search**.</span></span> <span data-ttu-id="c6557-128">Se mostrarán las ciudades cuyos nombres comienzan con en el **resultados de la búsqueda** sección de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="c6557-128">This displays cities whose names start with A in the **Search Results** section of the interface.</span></span>  
  
     ![](../core/media/86661144-c666-4d72-9227-9f17df715ba4.gif "86661144-c666-4d72-9227-9f17df715ba4")  
  
3.  <span data-ttu-id="c6557-129">Haga clic en una de las ubicaciones para obtener su información detallada.</span><span class="sxs-lookup"><span data-stu-id="c6557-129">Click one of the locations to get its detail information.</span></span> <span data-ttu-id="c6557-130">Por ejemplo, en la ilustración siguiente, el usuario hace clic en el **AUS01** vincular en el **Location Code** columna.</span><span class="sxs-lookup"><span data-stu-id="c6557-130">For example, in the figure below, the user clicked the **AUS01** link in the **Location Code** column.</span></span>  
  
4.  <span data-ttu-id="c6557-131">Escriba datos nuevos en uno de los campos (como el **dirección 2** campo) y haga clic en **guardar** en la esquina inferior izquierda.</span><span class="sxs-lookup"><span data-stu-id="c6557-131">Enter some new data into one of the fields (such as the **Address 2** field) and click **Save** in the lower-left corner.</span></span> <span data-ttu-id="c6557-132">En el registro se guardarán los datos recién especificados.</span><span class="sxs-lookup"><span data-stu-id="c6557-132">This saves the newly entered data into the record.</span></span>  
  
     ![](../core/media/b6eb137c-c0b0-4906-8fbd-1bc036069fb0.gif "b6eb137c-c0b0-4906-8fbd-1bc036069fb0")  
  
5.  <span data-ttu-id="c6557-133">Para comprobar si se el cambio se realizó correctamente, repita el proceso desde el paso 2, busque de nuevo el mismo registro y observe los cambios realizados en él.</span><span class="sxs-lookup"><span data-stu-id="c6557-133">To verify the success of this change, repeat the process from step 2, find this same record again, and observe the changes made to the record.</span></span>  
  
6.  <span data-ttu-id="c6557-134">En la parte superior derecha de la ventana, haga clic en **cerrar sesión** para finalizar la sesión de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="c6557-134">In the upper-right portion of the window, click **Sign out** to end your PeopleSoft session.</span></span>  
  
     ![](../core/media/7760b541-5155-453e-a682-4780412f3c13.gif "7760b541-5155-453e-a682-4780412f3c13")  
  
    > [!NOTE]
    >  <span data-ttu-id="c6557-135">En la práctica siguiente se incluye instrucciones para usar el adaptador de PeopleSoft con el fin de recuperar la información para el registro de ubicación (AUS01) que ha modificado.</span><span class="sxs-lookup"><span data-stu-id="c6557-135">In the next lab there are instructions for using the PeopleSoft adapter to retrieve the information for the location record (AUS01) that you modified.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="c6557-136">Resumen</span><span class="sxs-lookup"><span data-stu-id="c6557-136">Summary</span></span>  
 <span data-ttu-id="c6557-137">En esta práctica inició sesión en el sistema PeopleSoft a través de un explorador.</span><span class="sxs-lookup"><span data-stu-id="c6557-137">In this lab you logged on to the PeopleSoft system through a browser.</span></span> <span data-ttu-id="c6557-138">Una vez conectado, buscó datos y ha manipulado y actualizó el campo de dirección de un registro.</span><span class="sxs-lookup"><span data-stu-id="c6557-138">After you were connected, you searched for data, and then manipulated and updated a record's address field.</span></span> <span data-ttu-id="c6557-139">Después de validar el cambio, pudo ver los datos modificados en el explorador para comprobar que el cambio se había ejecutado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6557-139">After committing the change, you could view the modified data in the browser to verify that the change executed properly.</span></span>