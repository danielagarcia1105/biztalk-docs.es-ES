---
title: Habilitar el Coordinador de transacciones distribuidas de MS permitir las transacciones de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 634538e5-7292-4b3f-85b0-c6db86d0dbd2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0597c050e1531d71a62af04fe6c825653076297c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="enable-ms-distributed-transaction-coordinator-to-allow-transactions-for-oracle-e-business-suite"></a><span data-ttu-id="43354-102">Habilitar el Coordinador de transacciones distribuidas de MS permitir las transacciones de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="43354-102">Enable MS distributed transaction coordinator to allow transactions for Oracle E-Business Suite</span></span>
<span data-ttu-id="43354-103">Configurar MSDTC para comenzar a crear aplicaciones que usan el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43354-103">Configure MSDTC before you start creating applications that use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
<span data-ttu-id="43354-104">Las operaciones se realizan sobre el uso de Oracle E-Business Suite el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (a través de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el modelo de servicio WCF o el modelo de canal WCF) se pueden realizar en un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="43354-104">The operations performed on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the WCF service model, or the WCF channel model) can be performed within a transaction scope.</span></span> <span data-ttu-id="43354-105">Si el programa de cliente tiene más de un recurso transaccional como parte de la misma transacción, la transacción obtiene elevada a una transacción MSDTC.</span><span class="sxs-lookup"><span data-stu-id="43354-105">If the client program has more than one transactional resource as part of the same transaction, the transaction gets elevated to an MSDTC transaction.</span></span> <span data-ttu-id="43354-106">Para habilitar el adaptador realizar operaciones dentro del ámbito de una transacción MSDTC, configurar MSDTC en el equipo que ejecuta el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]y en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="43354-106">To enable the adapter to perform operations within the scope of an MSDTC transaction, configure MSDTC on the computer running the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], and on the Oracle E-Business Suite.</span></span> <span data-ttu-id="43354-107">Además, agregue MSDTC a la lista de excepciones en el firewall, lo que puede ser el Firewall de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="43354-107">Also, add MSDTC to the exceptions list in your firewall, which may be the built-in Windows Firewall.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="43354-108">Los pasos para configurar MSDTC varían para diferentes sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="43354-108">The steps to configure MSDTC vary for different operating systems.</span></span> <span data-ttu-id="43354-109">Los pasos enumerados en este tema se aplican al cliente de Windows y sistemas operativos Windows Server.</span><span class="sxs-lookup"><span data-stu-id="43354-109">The steps listed in this topic apply to Windows client and Windows Server operating systems.</span></span>  
  
## <a name="configure-msdtc"></a><span data-ttu-id="43354-110">Configurar MSDTC</span><span class="sxs-lookup"><span data-stu-id="43354-110">Configure MSDTC</span></span>  
  
1.  <span data-ttu-id="43354-111">Abra **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="43354-111">Open **Component Services**.</span></span>  

    <span data-ttu-id="43354-112">O bien, en **el administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="43354-112">Or, In **Server Manager**, select **Tools**, and then select **Component Services**.</span></span>  
  
2.  <span data-ttu-id="43354-113">Expanda **servicios de componentes**, expanda **equipos**, expanda **Mi PC**, expanda **Coordinador de transacciones distribuidas**, Haga clic en **DTC Local**y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="43354-113">Expand **Component Services**, expand **Computers**, expand **My Computer**, expand **Distributed Transaction Coordinator**, right-click **Local DTC**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="43354-114">Seleccione la pestaña **Seguridad** . En esta ficha, seleccione todos los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="43354-114">Select the **Security** tab. In this tab, select all of the following:</span></span> 

  - <span data-ttu-id="43354-115">**Acceso a DTC desde la red**</span><span class="sxs-lookup"><span data-stu-id="43354-115">**Network DTC Access**</span></span>
  - <span data-ttu-id="43354-116">**Permitir a clientes remotos**</span><span class="sxs-lookup"><span data-stu-id="43354-116">**Allow Remote Clients**</span></span> 
  - <span data-ttu-id="43354-117">**Permitir entrantes**</span><span class="sxs-lookup"><span data-stu-id="43354-117">**Allow Inbound**</span></span> 
  - <span data-ttu-id="43354-118">**Permitir salientes**</span><span class="sxs-lookup"><span data-stu-id="43354-118">**Allow Outbound**</span></span> 
  - <span data-ttu-id="43354-119">**No hay Authetnication necesario**</span><span class="sxs-lookup"><span data-stu-id="43354-119">**No Authetnication Required**</span></span>
  
4.  <span data-ttu-id="43354-120">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="43354-120">Select **OK** to save your changes.</span></span>  
  
5.  <span data-ttu-id="43354-121">Si se le pide que reinicie el servicio MSDTC, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="43354-121">If prompted to restarted the MSDTC service, select **Yes**.</span></span> <span data-ttu-id="43354-122">Una vez reiniciado el servicio MSDTC, cierre las propiedades y la MMC de servicios de componentes.</span><span class="sxs-lookup"><span data-stu-id="43354-122">After the MSDTC service is restarted, close the properties and the Component Services MMC.</span></span> 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a><span data-ttu-id="43354-123">Agregar MSDTC a la lista de excepciones de Firewall de Windows</span><span class="sxs-lookup"><span data-stu-id="43354-123">Add MSDTC to Windows Firewall exceptions list</span></span>  

> [!TIP] 
>  <span data-ttu-id="43354-124">Coordinador de transacción distribuida de Microsoft (MSDTC) se pueden permitirse ya en el firewall.</span><span class="sxs-lookup"><span data-stu-id="43354-124">Microsoft Distributed Tansaction Coordinator (MSDTC) may already be allowed in your firewall.</span></span> <span data-ttu-id="43354-125">Si es así, se muestra como una regla de entrada.</span><span class="sxs-lookup"><span data-stu-id="43354-125">If so, it is listed as an Inbound Rule.</span></span> <span data-ttu-id="43354-126">Si no aparece, use esta sección para permitir MSDTC.</span><span class="sxs-lookup"><span data-stu-id="43354-126">If it's not listed, use this section to allow MSDTC.</span></span> 

1.  <span data-ttu-id="43354-127">Abra **Firewall de Windows**y seleccione **configuración avanzada** a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="43354-127">Open **Windows Firewall**, and select **Advanced Settings** on the left.</span></span>  

    <span data-ttu-id="43354-128">O bien, en **el administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **Firewall de Windows con seguridad avanzada**.</span><span class="sxs-lookup"><span data-stu-id="43354-128">Or, In **Server Manager**, select **Tools**, and then select **Windows Firewall with Advanced Security**.</span></span>  
  
2.  <span data-ttu-id="43354-129">Haga clic en **reglas de entrada**y seleccione **nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="43354-129">Right click **Inbound Rules**, and select **New Rule**.</span></span>  
  
3.  <span data-ttu-id="43354-130">En el asistente:</span><span class="sxs-lookup"><span data-stu-id="43354-130">In the wizard:</span></span> 

    1. <span data-ttu-id="43354-131">Seleccione **programa**y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="43354-131">Select **Program**, and select **Next**.</span></span> 
    2. <span data-ttu-id="43354-132">Establecer el **la ruta del programa** a `%SystemRoot%\system32\msdtc.exe`y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="43354-132">Set the **program path** to `%SystemRoot%\system32\msdtc.exe`, and select **Next**.</span></span>  
    3. <span data-ttu-id="43354-133">**Permitir la conexión**y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="43354-133">**Allow the connection**, and select **Next**.</span></span>
    4. <span data-ttu-id="43354-134">Seleccione **dominio**y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="43354-134">Select **Domain**, and select **Next**.</span></span>
    5. <span data-ttu-id="43354-135">Escriba cualquier nombre, como `MSDTC for Oracle EBS`y seleccione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="43354-135">Enter any name, such as `MSDTC for Oracle EBS`, and select **Finish**.</span></span>
  
5.  <span data-ttu-id="43354-136">Complete el asistente y cierre Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="43354-136">Complete the wizard, and close Windows Firewall.</span></span> 
  
## <a name="next"></a><span data-ttu-id="43354-137">Siguiente</span><span class="sxs-lookup"><span data-stu-id="43354-137">Next</span></span> 
[<span data-ttu-id="43354-138">Ejemplos para el adaptador de Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="43354-138">Samples for the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)