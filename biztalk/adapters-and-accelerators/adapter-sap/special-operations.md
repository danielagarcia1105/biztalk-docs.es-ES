---
title: Operaciones especiales | Microsoft Docs
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
ms.openlocfilehash: 2bada45064e588748b25947e08b104dc79838ee0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975989"
---
# <a name="special-operations"></a><span data-ttu-id="fff7b-102">Operaciones especiales</span><span class="sxs-lookup"><span data-stu-id="fff7b-102">Special Operations</span></span>
<span data-ttu-id="fff7b-103">La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone varias operaciones especiales.</span><span class="sxs-lookup"><span data-stu-id="fff7b-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces several special operations.</span></span> <span data-ttu-id="fff7b-104">Estas operaciones no se basan en los artefactos del sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="fff7b-104">These operations are not based on SAP system artifacts.</span></span> <span data-ttu-id="fff7b-105">Emerge para proporcionar la funcionalidad para las aplicaciones de cliente del adaptador.</span><span class="sxs-lookup"><span data-stu-id="fff7b-105">They are surfaced to provide functionality for adapter client applications.</span></span> <span data-ttu-id="fff7b-106">Las operaciones especiales son:</span><span class="sxs-lookup"><span data-stu-id="fff7b-106">The special operations are:</span></span>  
  
- <span data-ttu-id="fff7b-107">**RfcGetAttributes**.</span><span class="sxs-lookup"><span data-stu-id="fff7b-107">**RfcGetAttributes**.</span></span> <span data-ttu-id="fff7b-108">Esta operación aparece bajo el nodo RFC y expone la funcionalidad de RFC SDK.</span><span class="sxs-lookup"><span data-stu-id="fff7b-108">This operation is surfaced under the RFC node and exposes functionality of the RFC SDK.</span></span> <span data-ttu-id="fff7b-109">Proporciona la siguiente información acerca de la conexión RFC:</span><span class="sxs-lookup"><span data-stu-id="fff7b-109">It provides the following information about the RFC connection:</span></span>  
  
  - <span data-ttu-id="fff7b-110">El identificador del sistema</span><span class="sxs-lookup"><span data-stu-id="fff7b-110">The system ID</span></span>  
  
  - <span data-ttu-id="fff7b-111">La página de códigos de socio</span><span class="sxs-lookup"><span data-stu-id="fff7b-111">The partner code page</span></span>  
  
  - <span data-ttu-id="fff7b-112">El lenguaje</span><span class="sxs-lookup"><span data-stu-id="fff7b-112">The language</span></span>  
  
    <span data-ttu-id="fff7b-113">Para obtener más información sobre la operación de RfcGetAttributes incluidos su esquema de mensaje, consulte [esquemas de mensaje para operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span><span class="sxs-lookup"><span data-stu-id="fff7b-113">For more information about the RfcGetAttributes operation including its message schema, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
- <span data-ttu-id="fff7b-114">**RfcConfirmTransID**.</span><span class="sxs-lookup"><span data-stu-id="fff7b-114">**RfcConfirmTransID**.</span></span> <span data-ttu-id="fff7b-115">Esta operación aparece bajo el nodo TRFC y expone la funcionalidad de RFC SDK.</span><span class="sxs-lookup"><span data-stu-id="fff7b-115">This operation is surfaced under the TRFC node and exposes RFC SDK functionality.</span></span> <span data-ttu-id="fff7b-116">Esta operación se utiliza para confirmar los identificadores de transacción de SAP en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="fff7b-116">You use this operation to confirm SAP transaction IDs on the SAP system.</span></span>  
  
   <span data-ttu-id="fff7b-117">Para obtener más información acerca de cómo usar la operación RfcConfirmTransID y sobre su esquema de mensaje, consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="fff7b-117">For more information about how to use the RfcConfirmTransID operation and about its message schema, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
- <span data-ttu-id="fff7b-118">**cadena SapAdapterUtilities.ConvertGuidToTid(Guid)**.</span><span class="sxs-lookup"><span data-stu-id="fff7b-118">**string SapAdapterUtilities.ConvertGuidToTid(Guid)**.</span></span> <span data-ttu-id="fff7b-119">Se trata de un método público expuesto por el ensamblado del adaptador SAP.</span><span class="sxs-lookup"><span data-stu-id="fff7b-119">This is a public method exposed by the SAP adapter assembly.</span></span> <span data-ttu-id="fff7b-120">(No es una operación obtenida por el adaptador.) Devuelve la transacción de SAP TID (Id.) se asignan con el GUID especificado.</span><span class="sxs-lookup"><span data-stu-id="fff7b-120">(It is not an operation surfaced by the adapter.) It returns the SAP transaction ID (TID) mapped to the specified GUID.</span></span>  
  
   <span data-ttu-id="fff7b-121">Internamente, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] asigna la transacción de SAP TID (Id.) que identifica una unidad lógica de trabajo (LUW) en el sistema SAP en un GUID.</span><span class="sxs-lookup"><span data-stu-id="fff7b-121">Internally, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] maps the SAP transaction ID (TID) that identifies a logical unit of work (LUW) on the SAP system to a GUID.</span></span> <span data-ttu-id="fff7b-122">Este GUID se expone a los clientes del adaptador, por lo que puede confirmar un tRFC (LUW) al invocar la operación RfcConfirmTransID para confirmar el TID en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="fff7b-122">This GUID is exposed to adapter clients, so that they can commit a tRFC (LUW) by invoking the RfcConfirmTransID operation to confirm its TID on the SAP system.</span></span>  
  
   <span data-ttu-id="fff7b-123">Sin embargo, para algunos escenarios, puede que necesite el TID que está asociado con un tRFC.</span><span class="sxs-lookup"><span data-stu-id="fff7b-123">However, for some scenarios, you may need the TID that is associated with a tRFC.</span></span> <span data-ttu-id="fff7b-124">Por ejemplo, desea identificar el LUW en el sistema SAP para solucionar un problema.</span><span class="sxs-lookup"><span data-stu-id="fff7b-124">For example, you may want to identify the LUW on the SAP system to troubleshoot an issue.</span></span> <span data-ttu-id="fff7b-125">Para estos escenarios se puede llamar a **ConvertGuidToTid**.</span><span class="sxs-lookup"><span data-stu-id="fff7b-125">For these scenarios you can call **ConvertGuidToTid**.</span></span> <span data-ttu-id="fff7b-126">Para usar **ConvertGuidToTid** en el código, debe agregar una referencia al ensamblado del adaptador SAP a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="fff7b-126">To use **ConvertGuidToTid** in your code, you must add a reference to the SAP adapter assembly to your project.</span></span>  
  
   <span data-ttu-id="fff7b-127">Para obtener más información sobre cómo invocar trfc, consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="fff7b-127">For more information about invoking tRFCs, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span> <span data-ttu-id="fff7b-128">El ejemplo siguiente muestra cómo invocar **ConvertGuidToTid**.</span><span class="sxs-lookup"><span data-stu-id="fff7b-128">The following example shows how to invoke **ConvertGuidToTid**.</span></span>  
  
  ```  
  // messageGuid is the GUID associated with a tRFC or IDOC  
  
  string tid = SapAdapterUtilities.ConvertGuidToTid(messageGuid);  
  ```  
  
## <a name="see-also"></a><span data-ttu-id="fff7b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="fff7b-129">See Also</span></span>  
 [<span data-ttu-id="fff7b-130">Los mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="fff7b-130">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)