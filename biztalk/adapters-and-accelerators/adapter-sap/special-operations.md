---
title: Operaciones especiales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, special operations surfaced by the SAP adapter
ms.assetid: 8725fe63-6ff4-49c8-b386-d4c67e2be440
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe2472d905e9e726b827d44da79bdfe840233354
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="special-operations"></a><span data-ttu-id="6ef36-102">Operaciones especiales</span><span class="sxs-lookup"><span data-stu-id="6ef36-102">Special Operations</span></span>
<span data-ttu-id="6ef36-103">La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone varias operaciones especiales.</span><span class="sxs-lookup"><span data-stu-id="6ef36-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces several special operations.</span></span> <span data-ttu-id="6ef36-104">Estas operaciones no se basan en artefactos del sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="6ef36-104">These operations are not based on SAP system artifacts.</span></span> <span data-ttu-id="6ef36-105">Emerge para proporcionar la funcionalidad para las aplicaciones de cliente de adaptador.</span><span class="sxs-lookup"><span data-stu-id="6ef36-105">They are surfaced to provide functionality for adapter client applications.</span></span> <span data-ttu-id="6ef36-106">Las operaciones especiales son:</span><span class="sxs-lookup"><span data-stu-id="6ef36-106">The special operations are:</span></span>  
  
-   <span data-ttu-id="6ef36-107">**RfcGetAttributes**.</span><span class="sxs-lookup"><span data-stu-id="6ef36-107">**RfcGetAttributes**.</span></span> <span data-ttu-id="6ef36-108">Esta operación aparece bajo el nodo RFC y expone la funcionalidad de RFC SDK.</span><span class="sxs-lookup"><span data-stu-id="6ef36-108">This operation is surfaced under the RFC node and exposes functionality of the RFC SDK.</span></span> <span data-ttu-id="6ef36-109">Proporciona la siguiente información acerca de la conexión de RFC:</span><span class="sxs-lookup"><span data-stu-id="6ef36-109">It provides the following information about the RFC connection:</span></span>  
  
    -   <span data-ttu-id="6ef36-110">El identificador del sistema</span><span class="sxs-lookup"><span data-stu-id="6ef36-110">The system ID</span></span>  
  
    -   <span data-ttu-id="6ef36-111">La página de códigos de socio comercial</span><span class="sxs-lookup"><span data-stu-id="6ef36-111">The partner code page</span></span>  
  
    -   <span data-ttu-id="6ef36-112">El idioma</span><span class="sxs-lookup"><span data-stu-id="6ef36-112">The language</span></span>  
  
     <span data-ttu-id="6ef36-113">Para obtener más información sobre la operación de RfcGetAttributes incluidos su esquema de mensaje, consulte [esquemas de mensaje para las operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span><span class="sxs-lookup"><span data-stu-id="6ef36-113">For more information about the RfcGetAttributes operation including its message schema, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
-   <span data-ttu-id="6ef36-114">**RfcConfirmTransID**.</span><span class="sxs-lookup"><span data-stu-id="6ef36-114">**RfcConfirmTransID**.</span></span> <span data-ttu-id="6ef36-115">Esta operación aparece bajo el nodo TRFC y expone la funcionalidad de RFC SDK.</span><span class="sxs-lookup"><span data-stu-id="6ef36-115">This operation is surfaced under the TRFC node and exposes RFC SDK functionality.</span></span> <span data-ttu-id="6ef36-116">Use esta operación para confirmar los identificadores de transacción de SAP en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="6ef36-116">You use this operation to confirm SAP transaction IDs on the SAP system.</span></span>  
  
     <span data-ttu-id="6ef36-117">Para obtener más información acerca de cómo usar la operación de RfcConfirmTransID y sobre su esquema de mensaje, vea [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="6ef36-117">For more information about how to use the RfcConfirmTransID operation and about its message schema, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
-   <span data-ttu-id="6ef36-118">**cadena SapAdapterUtilities.ConvertGuidToTid(Guid)**.</span><span class="sxs-lookup"><span data-stu-id="6ef36-118">**string SapAdapterUtilities.ConvertGuidToTid(Guid)**.</span></span> <span data-ttu-id="6ef36-119">Se trata de un método público expuesto por el ensamblado de adaptador SAP.</span><span class="sxs-lookup"><span data-stu-id="6ef36-119">This is a public method exposed by the SAP adapter assembly.</span></span> <span data-ttu-id="6ef36-120">(No es una operación obtenida por el adaptador.) Devuelve la transacción de SAP identificador (TID) asignado para el GUID especificado.</span><span class="sxs-lookup"><span data-stu-id="6ef36-120">(It is not an operation surfaced by the adapter.) It returns the SAP transaction ID (TID) mapped to the specified GUID.</span></span>  
  
     <span data-ttu-id="6ef36-121">Internamente, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] asigna la transacción de SAP TID (Id.) que identifica una unidad lógica de trabajo (LUW) en el sistema SAP en un GUID.</span><span class="sxs-lookup"><span data-stu-id="6ef36-121">Internally, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] maps the SAP transaction ID (TID) that identifies a logical unit of work (LUW) on the SAP system to a GUID.</span></span> <span data-ttu-id="6ef36-122">Este GUID se expone a los clientes de adaptador, por lo que puede confirmar una tRFC (LUW) mediante la invocación de la operación de RfcConfirmTransID para confirmar su TID en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="6ef36-122">This GUID is exposed to adapter clients, so that they can commit a tRFC (LUW) by invoking the RfcConfirmTransID operation to confirm its TID on the SAP system.</span></span>  
  
     <span data-ttu-id="6ef36-123">Sin embargo, para algunos escenarios, puede que tenga el TID que está asociado a un tRFC.</span><span class="sxs-lookup"><span data-stu-id="6ef36-123">However, for some scenarios, you may need the TID that is associated with a tRFC.</span></span> <span data-ttu-id="6ef36-124">Por ejemplo, puede que desee identificar el LUW en el sistema SAP para solucionar un problema.</span><span class="sxs-lookup"><span data-stu-id="6ef36-124">For example, you may want to identify the LUW on the SAP system to troubleshoot an issue.</span></span> <span data-ttu-id="6ef36-125">En estos casos puede llamar a **ConvertGuidToTid**.</span><span class="sxs-lookup"><span data-stu-id="6ef36-125">For these scenarios you can call **ConvertGuidToTid**.</span></span> <span data-ttu-id="6ef36-126">Usar **ConvertGuidToTid** en el código, debe agregar una referencia al ensamblado del adaptador SAP para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6ef36-126">To use **ConvertGuidToTid** in your code, you must add a reference to the SAP adapter assembly to your project.</span></span>  
  
     <span data-ttu-id="6ef36-127">Para obtener más información sobre cómo invocar tRFCs, consulte [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="6ef36-127">For more information about invoking tRFCs, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span> <span data-ttu-id="6ef36-128">En el ejemplo siguiente se muestra cómo invocar **ConvertGuidToTid**.</span><span class="sxs-lookup"><span data-stu-id="6ef36-128">The following example shows how to invoke **ConvertGuidToTid**.</span></span>  
  
    ```  
    // messageGuid is the GUID associated with a tRFC or IDOC  
  
    string tid = SapAdapterUtilities.ConvertGuidToTid(messageGuid);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6ef36-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ef36-129">See Also</span></span>  
 [<span data-ttu-id="6ef36-130">Mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="6ef36-130">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)