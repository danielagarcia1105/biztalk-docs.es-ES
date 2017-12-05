---
title: "Configuración de propiedades comunes de reserva para X12 y EDIFACT los mensajes codificados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7393d6ac-b901-43ef-a8d6-c5b0b3033257
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b99d6e60a2a5955a9f0873156dbc5f822b3d519
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages"></a><span data-ttu-id="fced7-102">Configuración de las propiedades comunes de reserva para mensajes codificados en X12 y EDIFACT</span><span class="sxs-lookup"><span data-stu-id="fced7-102">Configuring Common Fallback Properties for X12 and EDIFACT Encoded Messages</span></span>
<span data-ttu-id="fced7-103">Las propiedades de reserva se aplican tanto a intercambios X12 (incluido HIPAA) como a intercambios con codificación EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="fced7-103">Fallback properties apply to both X12 (including HIPAA) - and EDIFACT-encoded interchanges.</span></span> <span data-ttu-id="fced7-104">Al igual que sucede con las propiedades del acuerdo de reserva, estas propiedades solamente se aplican si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha determinado el acuerdo en el cual se resuelve el mensaje de entrada o salida.</span><span class="sxs-lookup"><span data-stu-id="fced7-104">As with all fallback agreement properties, these properties apply only when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has not determined the agreement to which an incoming our outgoing message resolves to.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fced7-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fced7-105">Prerequisites</span></span>  
 <span data-ttu-id="fced7-106">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fced7-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-common-global-properties"></a><span data-ttu-id="fced7-107">Para establecer propiedades globales comunes</span><span class="sxs-lookup"><span data-stu-id="fced7-107">To set common global properties</span></span>  
  
1.  <span data-ttu-id="fced7-108">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva** o **configuración de reserva de EDIFACT**.</span><span class="sxs-lookup"><span data-stu-id="fced7-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings** or **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="fced7-109">En el **páginas generales de configuración de reserva** ficha la **General** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fced7-109">In the **Fallback Settings General Pages** tab, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="fced7-110">Haga clic en **habilitar la configuración de reserva** para habilitar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para utilizar la configuración de acuerdo de reserva si no hay ningún acuerdo se resuelve para mensajes entrantes o salientes.</span><span class="sxs-lookup"><span data-stu-id="fced7-110">Click **Enable Fallback Settings** to enable [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use the fallback agreement settings if no agreement is resolved for incoming or outgoing messages.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="fced7-111">Si no se activa esta opción, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no usará las propiedades configuradas en el acuerdo de reserva.</span><span class="sxs-lookup"><span data-stu-id="fced7-111">If this option is not checked, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will not use the properties set in the fallback agreement.</span></span>  
  
    2.  <span data-ttu-id="fced7-112">Haga clic en **activar informes de EDI** para activar los informes para todos los mensajes EDI.</span><span class="sxs-lookup"><span data-stu-id="fced7-112">Click **Activate EDI Reporting** to activate reporting for all EDI messages.</span></span> <span data-ttu-id="fced7-113">Esto garantiza que los mensajes se muestran en el estado de informes de las pantallas mostradas, haga clic en los vínculos situados en la parte inferior de la **concentrador de grupo** panel de la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fced7-113">This ensures messages are displayed in the status reporting screens displayed by clicking the links at the bottom of the **Group Hub** pane of the BizTalk Server Administration Console.</span></span>  
  
    3.  <span data-ttu-id="fced7-114">Si hace clic en **activar informes de EDI**, haga clic en **almacenar carga y conjunto de transacciones para los informes** almacenar transacciones se establece en las tablas EDI de la base de datos de seguimiento (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="fced7-114">If you clicked **Activate EDI Reporting**, click **Store transaction set/payload for reporting** to store transaction sets in the EDI tables of the tracking (BizTalkDTADb) database.</span></span>  
  
    4.  <span data-ttu-id="fced7-115">Haga clic en **registrar errores y advertencias generados por el motor EDI en el registro de eventos de Windows** para registrar los mensajes de error/advertencia generados por el motor de EDI (canalizaciones de EDI, procesamiento por lotes de orquestación, orquestación de enrutamiento, etc.), junto con contextuales información en el Visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="fced7-115">Click **Log EDI errors and warnings generated by EDI engine to Windows event log** to log error/warnings messages generated by the EDI engine (EDI pipelines, batching orchestration, routing orchestration, etc.), with contextual information, to the Windows Event Viewer.</span></span> <span data-ttu-id="fced7-116">Si se desactiva, estos mensajes de error o de advertencia no se registrarán en el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="fced7-116">If cleared, these error/warning messages will not be logged to the Event Viewer.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fced7-117">Los errores del sistema o de procesamiento se registran en el Visor de eventos independientemente de si está activada o no la casilla.</span><span class="sxs-lookup"><span data-stu-id="fced7-117">System/processing errors are logged in the Event Viewer whether or not this checkbox is selected.</span></span>  
  
3.  <span data-ttu-id="fced7-118">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar y aceptar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fced7-118">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate and accept the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fced7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fced7-119">See Also</span></span>  
 [<span data-ttu-id="fced7-120">Configuración de las propiedades de acuerdos globales o de respaldo</span><span class="sxs-lookup"><span data-stu-id="fced7-120">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)