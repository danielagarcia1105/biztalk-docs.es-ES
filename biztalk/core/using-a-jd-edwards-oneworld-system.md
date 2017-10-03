---
title: Uso del sistema JD Edwards OneWorld | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5346aa04-ebd7-4545-9062-b349fd73b7f1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 835432e50bce3f347e6f769fb8182ab35fc4f949
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="44a30-102">Uso del sistema JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="44a30-102">Using a JD Edwards OneWorld System</span></span>
<span data-ttu-id="44a30-103">El adaptador de JD Edwards OneWorld permite obtener acceso al sistema JD Edwards OneWorld desde un sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44a30-103">The JD Edwards OneWorld system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="44a30-104">Este adaptador pertenece a un grupo de ocho adaptadores de línea empresarial (LOB) que Microsoft distribuye para su uso con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44a30-104">This adapter is one of a group of eight line-of-business (LOB) adapters shipped by Microsoft for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="44a30-105">El trabajo de práctico de JD Edwards OneWorld se divide en dos partes.</span><span class="sxs-lookup"><span data-stu-id="44a30-105">The JD Edwards OneWorld lab work is divided into two parts.</span></span> <span data-ttu-id="44a30-106">La primera práctica (Práctica 1) le permite usar el sistema JD Edwards OneWorld sin necesidad de contar con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o alguno de los productos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="44a30-106">This first lab (Lab 1) allows you to use the JD Edwards OneWorld system without needing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any Microsoft products.</span></span> <span data-ttu-id="44a30-107">Podrá usar la herramienta JD Edwards OneWorld Client para conectarse a una base de datos de JD Edwards OneWorld y localizar registros específicos basados en direcciones.</span><span class="sxs-lookup"><span data-stu-id="44a30-107">You will use the JD Edwards OneWorld Client tool to connect to a JD Edwards OneWorld database and locate a specific record based upon address.</span></span>  
  
 <span data-ttu-id="44a30-108">En la segunda práctica (Práctica 2), creará un proyecto y una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="44a30-108">In the second lab (Lab 2), you will create a BizTalk project and orchestration.</span></span> <span data-ttu-id="44a30-109">Después de crear la aplicación, la implementará y usará para conectarse a un sistema JD Edwards OneWorld mediante el adaptador de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="44a30-109">After you create the application, you will deploy it and use it to connect to a JD Edwards OneWorld system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="44a30-110">El objetivo es obtener acceso a los datos a través de la aplicación BizTalk mediante el adaptador.</span><span class="sxs-lookup"><span data-stu-id="44a30-110">The goal is to access data through the BizTalk application by using the adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="44a30-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="44a30-111">Prerequisites</span></span>  
 <span data-ttu-id="44a30-112">Para realizar el procedimiento de esta práctica, deberá instalar el software cliente de JD Edwards OneWorld y su actualización más reciente.</span><span class="sxs-lookup"><span data-stu-id="44a30-112">To perform the procedures for this lab, you need to install the JD Edwards OneWorld client software and its latest update.</span></span> <span data-ttu-id="44a30-113">Para usar las herramientas del software cliente, deberá tener una base de datos de JD Edwards OneWorld, conectividad de red para tal base de datos y una cuenta de usuario en ese sistema.</span><span class="sxs-lookup"><span data-stu-id="44a30-113">To use any of the client software tools you will need a JD Edwards OneWorld database, network connectivity to that database, and a user account on that system.</span></span> <span data-ttu-id="44a30-114">No es necesario contar con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para completar esta práctica.</span><span class="sxs-lookup"><span data-stu-id="44a30-114">You do not need [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to complete this lab.</span></span>  
  
## <a name="lab-1---using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="44a30-115">Práctica 1: uso del sistema JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="44a30-115">Lab 1 - Using a JD Edwards OneWorld System</span></span>  
 <span data-ttu-id="44a30-116">En esta práctica, usará el sistema JD Edwards OneWorld sin necesidad de usar componentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44a30-116">In this lab, you will use the JD Edwards OneWorld system without using any components of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="44a30-117">Los objetivos son probar la conectividad con JD Edwards OneWorld y garantizar que la segunda práctica funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="44a30-117">The goals are to test your connectivity to JD Edwards OneWorld and to ensure that the second lab will work correctly.</span></span> <span data-ttu-id="44a30-118">Usará la herramienta JD Edwards OneWorld SQL Plus para crear y manipular una tabla de datos en una base de datos de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="44a30-118">You will use the JD Edwards OneWorld SQL Plus tool to create and manipulate a data table in a JD Edwards OneWorld database.</span></span>  
  
## <a name="procedures-for-lab-1---using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="44a30-119">Procedimientos para la Práctica 1: uso del sistema JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="44a30-119">Procedures for Lab 1 - Using a JD Edwards OneWorld System</span></span>  
  
#### <a name="to-log-on-to-jd-edwards-oneworld-by-using-a-browser"></a><span data-ttu-id="44a30-120">Iniciar sesión en JD Edwards OneWorld mediante un explorador</span><span class="sxs-lookup"><span data-stu-id="44a30-120">To log on to JD Edwards OneWorld by using a browser</span></span>  
  
-   <span data-ttu-id="44a30-121">Inicie sesión en el sistema JD Edwards OneWorld haciendo clic en el icono JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="44a30-121">Log on to the JD Edwards OneWorld system by clicking the JD Edwards OneWorld icon.</span></span> <span data-ttu-id="44a30-122">Escriba su **Id. de usuario**, **contraseña**, y **entorno**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="44a30-122">Enter your **User ID**, **Password**, and **Environment**, and then click **OK**.</span></span>  
  
     ![](../core/media/f04db2ef-d587-4357-b9e8-c96319886e97.gif "f04db2ef-d587-4357-b9e8-c96319886e97")  
  
#### <a name="to-locate-and-view-jd-edwards-oneworld-data"></a><span data-ttu-id="44a30-123">Localizar y ver datos de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="44a30-123">To locate and view JD Edwards OneWorld data</span></span>  
  
1.  <span data-ttu-id="44a30-124">Si inicia sesión correctamente, mostrará el **JD Edwards OneWorld Explorer**.</span><span class="sxs-lookup"><span data-stu-id="44a30-124">A successful logon places you at the **JD Edwards OneWorld Explorer**.</span></span>  
  
     ![](../core/media/14e8c206-7e38-48f8-9108-e32a7ac9a740.gif "14e8c206-7e38-48f8-9108-e32a7ac9a740")  
  
2.  <span data-ttu-id="44a30-125">Expanda **directorio maestro**, a continuación, **Foundation sistemas**, a continuación, **libreta de direcciones**y, a continuación, **procesamiento diario**.</span><span class="sxs-lookup"><span data-stu-id="44a30-125">Expand **Master Directory**, then **Foundation Systems**, then **Address Book**, and then **Daily Processing**.</span></span>  
  
     ![](../core/media/1f742221-00e5-4697-95ff-64aa63ed567a.gif "1f742221-00e5-4697-95ff-64aa63ed567a")  
  
3.  <span data-ttu-id="44a30-126">En la ventana de la derecha, haga doble clic en **revisiones de la libreta de direcciones**.</span><span class="sxs-lookup"><span data-stu-id="44a30-126">In the right-hand window, double-click **Address Book Revisions**.</span></span>  
  
     ![](../core/media/a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031.gif "a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031")  
  
4.  <span data-ttu-id="44a30-127">Para **nombre alfa**, escriba `Ga`, seleccione la **para mostrar la dirección** casilla de verificación y, a continuación, haga clic en **buscar** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="44a30-127">For **Alpha Name**, enter `Ga`, select the **Display Address** check box, and then click **Find** on the toolbar.</span></span>  
  
     ![](../core/media/2f58413f-41a9-4ed9-ba5c-1d6d59eafb01.gif "2f58413f-41a9-4ed9-ba5c-1d6d59eafb01")  
  
     <span data-ttu-id="44a30-128">En el **revisiones de la libreta de direcciones - [trabajar con direcciones]** cuadro de diálogo, se muestran dos registros como resultado de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="44a30-128">In the **Address Book Revisions - [Work With Addresses]** dialog box, two records are displayed as a result of the search.</span></span>  
  
     ![](../core/media/9284df4e-ca9b-48ab-b2bf-a90d765d4a05.gif "9284df4e-ca9b-48ab-b2bf-a90d765d4a05")  
  
     <span data-ttu-id="44a30-129">Un método alternativo de localización de datos es borrar la **nombre alfa** , a continuación, haga clic en el cuadro de texto anterior la **número de dirección** columna y escriba `500`.</span><span class="sxs-lookup"><span data-stu-id="44a30-129">An alternative method of locating data is to clear the **Alpha Name** field, click in the text box above the **Address Number** column, and enter `500`.</span></span> <span data-ttu-id="44a30-130">Haga clic en **buscar** en la barra de herramientas para mostrar los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="44a30-130">Click **Find** on the toolbar to display the search results.</span></span>  
  
     ![](../core/media/a88bd867-9a16-416a-a43e-cdfcc65fc670.gif "a88bd867-9a16-416a-a43e-cdfcc65fc670")  
  
     <span data-ttu-id="44a30-131">En la práctica 2, se proporcionarán instrucciones para usar el adaptador de JD Edwards OneWorld para recuperar la información de un **número de dirección** de `500`.</span><span class="sxs-lookup"><span data-stu-id="44a30-131">In Lab 2, there will be instructions for using the JD Edwards OneWorld adapter to retrieve the information for an **Address Number** of `500`.</span></span>  
  
5.  <span data-ttu-id="44a30-132">En el **archivo** menú, haga clic en **salir** para salir de la sesión de JD Edwards OneWorld Client.</span><span class="sxs-lookup"><span data-stu-id="44a30-132">On the **File** menu, click **Exit** to exit the JE Edwards OneWorld Client session.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="44a30-133">Resumen</span><span class="sxs-lookup"><span data-stu-id="44a30-133">Summary</span></span>  
 <span data-ttu-id="44a30-134">En esta práctica, usó la herramienta JD Edwards OneWorld Client para iniciar sesión en el sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="44a30-134">In this lab, you used the JD Edwards OneWorld Client tool to log on to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="44a30-135">Una vez establecida la conexión, buscó datos específicos y vio los registros de datos devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="44a30-135">After you were connected, you searched for specific data and viewed the data records returned.</span></span>