---
title: Habilitar el Coordinador de transacciones distribuidas de MS permitir que las transacciones de Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 634538e5-7292-4b3f-85b0-c6db86d0dbd2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53037e9a7dc1ccc3c0ef21860696060ad1c046a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984997"
---
# <a name="enable-ms-distributed-transaction-coordinator-to-allow-transactions-for-oracle-e-business-suite"></a><span data-ttu-id="8f00f-102">Habilitar el Coordinador de transacciones distribuidas de MS permitir que las transacciones de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="8f00f-102">Enable MS distributed transaction coordinator to allow transactions for Oracle E-Business Suite</span></span>
<span data-ttu-id="8f00f-103">Configurar MSDTC antes de empezar a crear aplicaciones que usan el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f00f-103">Configure MSDTC before you start creating applications that use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
<span data-ttu-id="8f00f-104">Las operaciones se realizan sobre el uso de Oracle E-Business Suite el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (a través de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el modelo de servicio WCF o el modelo de canal WCF) se pueden realizar en un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="8f00f-104">The operations performed on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the WCF service model, or the WCF channel model) can be performed within a transaction scope.</span></span> <span data-ttu-id="8f00f-105">Si el programa cliente tiene más de un recurso transaccional como parte de la misma transacción, la transacción obtiene elevada a una transacción MSDTC.</span><span class="sxs-lookup"><span data-stu-id="8f00f-105">If the client program has more than one transactional resource as part of the same transaction, the transaction gets elevated to an MSDTC transaction.</span></span> <span data-ttu-id="8f00f-106">Para habilitar el adaptador realizar operaciones dentro del ámbito de una transacción MSDTC, configure MSDTC del equipo que ejecuta el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]y en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="8f00f-106">To enable the adapter to perform operations within the scope of an MSDTC transaction, configure MSDTC on the computer running the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], and on the Oracle E-Business Suite.</span></span> <span data-ttu-id="8f00f-107">También, agregar MSDTC a la lista de excepciones en el firewall, lo que puede ser el Firewall de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="8f00f-107">Also, add MSDTC to the exceptions list in your firewall, which may be the built-in Windows Firewall.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="8f00f-108">Los pasos para configurar MSDTC varían para diferentes sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="8f00f-108">The steps to configure MSDTC vary for different operating systems.</span></span> <span data-ttu-id="8f00f-109">Los pasos indicados en este tema se aplican al cliente de Windows y sistemas operativos Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8f00f-109">The steps listed in this topic apply to Windows client and Windows Server operating systems.</span></span>  
  
## <a name="configure-msdtc"></a><span data-ttu-id="8f00f-110">Configurar MSDTC</span><span class="sxs-lookup"><span data-stu-id="8f00f-110">Configure MSDTC</span></span>  
  
1. <span data-ttu-id="8f00f-111">Abra **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="8f00f-111">Open **Component Services**.</span></span>  

   <span data-ttu-id="8f00f-112">O bien, en **administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="8f00f-112">Or, In **Server Manager**, select **Tools**, and then select **Component Services**.</span></span>  
  
2. <span data-ttu-id="8f00f-113">Expanda **servicios de componentes**, expanda **equipos**, expanda **Mi PC**, expanda **Coordinador de transacciones distribuidas**, Haga clic en **DTC Local**y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8f00f-113">Expand **Component Services**, expand **Computers**, expand **My Computer**, expand **Distributed Transaction Coordinator**, right-click **Local DTC**, and select **Properties**.</span></span>  
  
3. <span data-ttu-id="8f00f-114">Seleccione la pestaña **Seguridad** . En esta pestaña, seleccione todos los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f00f-114">Select the **Security** tab. In this tab, select all of the following:</span></span> 

   - <span data-ttu-id="8f00f-115">**Acceso a DTC desde la red**</span><span class="sxs-lookup"><span data-stu-id="8f00f-115">**Network DTC Access**</span></span>
   - <span data-ttu-id="8f00f-116">**Permitir a clientes remotos**</span><span class="sxs-lookup"><span data-stu-id="8f00f-116">**Allow Remote Clients**</span></span> 
   - <span data-ttu-id="8f00f-117">**Permitir entrantes**</span><span class="sxs-lookup"><span data-stu-id="8f00f-117">**Allow Inbound**</span></span> 
   - <span data-ttu-id="8f00f-118">**Permitir salientes**</span><span class="sxs-lookup"><span data-stu-id="8f00f-118">**Allow Outbound**</span></span> 
   - <span data-ttu-id="8f00f-119">**No hay Authetnication necesario**</span><span class="sxs-lookup"><span data-stu-id="8f00f-119">**No Authetnication Required**</span></span>
  
4. <span data-ttu-id="8f00f-120">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="8f00f-120">Select **OK** to save your changes.</span></span>  
  
5. <span data-ttu-id="8f00f-121">Si se le pide que reinicie el servicio MSDTC, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="8f00f-121">If prompted to restarted the MSDTC service, select **Yes**.</span></span> <span data-ttu-id="8f00f-122">Después de reinicia el servicio MSDTC, cierre las propiedades y los servicios de componentes de MMC.</span><span class="sxs-lookup"><span data-stu-id="8f00f-122">After the MSDTC service is restarted, close the properties and the Component Services MMC.</span></span> 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a><span data-ttu-id="8f00f-123">Agregar MSDTC a la lista de excepciones de Firewall de Windows</span><span class="sxs-lookup"><span data-stu-id="8f00f-123">Add MSDTC to Windows Firewall exceptions list</span></span>  

> [!TIP] 
>  <span data-ttu-id="8f00f-124">Coordinador de transacción distribuida de Microsoft (MSDTC) puede que ya se permitidas en el firewall.</span><span class="sxs-lookup"><span data-stu-id="8f00f-124">Microsoft Distributed Tansaction Coordinator (MSDTC) may already be allowed in your firewall.</span></span> <span data-ttu-id="8f00f-125">Si es así, aparece como una regla de entrada.</span><span class="sxs-lookup"><span data-stu-id="8f00f-125">If so, it is listed as an Inbound Rule.</span></span> <span data-ttu-id="8f00f-126">Si no aparece, use esta sección para permitir MSDTC.</span><span class="sxs-lookup"><span data-stu-id="8f00f-126">If it's not listed, use this section to allow MSDTC.</span></span> 

1.  <span data-ttu-id="8f00f-127">Abra **Windows Firewall**y seleccione **configuración avanzada** a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="8f00f-127">Open **Windows Firewall**, and select **Advanced Settings** on the left.</span></span>  

    <span data-ttu-id="8f00f-128">O bien, en **administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **Firewall de Windows con seguridad avanzada**.</span><span class="sxs-lookup"><span data-stu-id="8f00f-128">Or, In **Server Manager**, select **Tools**, and then select **Windows Firewall with Advanced Security**.</span></span>  
  
2.  <span data-ttu-id="8f00f-129">Haga clic en **reglas de entrada**y seleccione **nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="8f00f-129">Right click **Inbound Rules**, and select **New Rule**.</span></span>  
  
3.  <span data-ttu-id="8f00f-130">En el asistente:</span><span class="sxs-lookup"><span data-stu-id="8f00f-130">In the wizard:</span></span> 

    1. <span data-ttu-id="8f00f-131">Seleccione **programa**y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8f00f-131">Select **Program**, and select **Next**.</span></span> 
    2. <span data-ttu-id="8f00f-132">Establecer el **ruta del programa** a `%SystemRoot%\system32\msdtc.exe`y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8f00f-132">Set the **program path** to `%SystemRoot%\system32\msdtc.exe`, and select **Next**.</span></span>  
    3. <span data-ttu-id="8f00f-133">**Permitir la conexión**y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8f00f-133">**Allow the connection**, and select **Next**.</span></span>
    4. <span data-ttu-id="8f00f-134">Seleccione **dominio**y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8f00f-134">Select **Domain**, and select **Next**.</span></span>
    5. <span data-ttu-id="8f00f-135">Escriba cualquier nombre, como `MSDTC for Oracle EBS`y seleccione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="8f00f-135">Enter any name, such as `MSDTC for Oracle EBS`, and select **Finish**.</span></span>
  
5.  <span data-ttu-id="8f00f-136">Complete el asistente y cierre Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="8f00f-136">Complete the wizard, and close Windows Firewall.</span></span> 
  
## <a name="next"></a><span data-ttu-id="8f00f-137">Siguiente</span><span class="sxs-lookup"><span data-stu-id="8f00f-137">Next</span></span> 
[<span data-ttu-id="8f00f-138">Ejemplos para el adaptador de Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="8f00f-138">Samples for the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)