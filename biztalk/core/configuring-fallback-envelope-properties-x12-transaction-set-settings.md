---
title: Configuración de las propiedades de sobres de reserva (configuración de conjunto de transacciones de X12) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a951f70-07d5-4a58-b1ea-e7117a45c545
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6225a931a991d4b4fb85a23525c53fe01f9e52db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021377"
---
# <a name="configuring-fallback-envelope-properties-x12-transaction-set-settings"></a><span data-ttu-id="2f9d9-102">Configuración de propiedades de sobres de reserva (configuración del conjunto de transacciones X12)</span><span class="sxs-lookup"><span data-stu-id="2f9d9-102">Configuring Fallback Envelope Properties (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="2f9d9-103">En el **sobres** página de la **configuración del conjunto de transacciones** sección, defina cómo BizTalk Server genera los segmentos GS de un intercambio codificado en X12 que envía a la entidad.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the GS segments for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="2f9d9-104">El segmento GS identifica y especifica un grupo funcional para un intercambio con codificación X12.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-104">A GS segment identifies and specifies a functional group for an X12-encoded interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f9d9-105">Este tema se aplica también a valores de configuración relacionados con HIPAA.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-105">This topic applies also to HIPAA-related settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2f9d9-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2f9d9-106">Prerequisites</span></span>  
 <span data-ttu-id="2f9d9-107">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f9d9-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-gs-segments"></a><span data-ttu-id="2f9d9-108">Procedimiento para definir segmentos GS</span><span class="sxs-lookup"><span data-stu-id="2f9d9-108">To define the GS segments</span></span>  
  
1. <span data-ttu-id="2f9d9-109">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="2f9d9-110">En el **X12 configuración de reserva** cuadro de diálogo el **X12 páginas del acuerdo** , bajo el **configuración del conjunto de transacciones** sección, haga clic en **sobres**.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3. <span data-ttu-id="2f9d9-111">Para **código funcional (GS01)**, seleccione un valor de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-111">For **Functional code (GS01)**, select a value from the drop-down list.</span></span>  
  
4. <span data-ttu-id="2f9d9-112">Para **remitente de la aplicación (GS02)**, escriba un valor alfanumérico con un mínimo de 2 y un máximo de 15.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-112">For **Application sender (GS02)**, enter an alphanumeric value with a minimum of 2 and a maximum of 15.</span></span> <span data-ttu-id="2f9d9-113">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-113">This is a required field.</span></span>  
  
5. <span data-ttu-id="2f9d9-114">Para **receptor de aplicación (GS03)**, escriba un valor alfanumérico con un mínimo de 2 y un máximo de 15.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-114">For **Application receiver (GS03)**, enter an alphanumeric value with a minimum of 2 and a maximum of 15.</span></span> <span data-ttu-id="2f9d9-115">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-115">This is a required field.</span></span>  
  
6. <span data-ttu-id="2f9d9-116">Para **formato de fecha (GS04)**, seleccione SSAAMMDD o AAMMDD en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-116">For **Date format (GS04)**, select CCYYMMDD or YYMMDD from the drop-down list.</span></span> <span data-ttu-id="2f9d9-117">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-117">This is a required field.</span></span>  
  
7. <span data-ttu-id="2f9d9-118">Para **formato de hora (GS05)**, seleccione HHMM, HHMMSS o HHMMSSdd de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-118">For **Time format (GS05)**, select HHMM, HHMMSS, or HHMMSSdd from the drop-down list.</span></span> <span data-ttu-id="2f9d9-119">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-119">This is a required field.</span></span>  
  
8. <span data-ttu-id="2f9d9-120">Para **Agencia responsable (GS07)**, seleccione el valor de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-120">For **Responsible agency (GS07)**, select the value from the drop-down list.</span></span>  
  
9. <span data-ttu-id="2f9d9-121">Para **identificador de documento (GS08)**, escriba un valor alfanumérico con un mínimo de 1 y un máximo de 12.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-121">For **Document identifier (GS08)**, enter an alphanumeric value with a minimum of 1 and a maximum of 12.</span></span> <span data-ttu-id="2f9d9-122">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-122">This is an optional field.</span></span>  
  
10. <span data-ttu-id="2f9d9-123">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2f9d9-123">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f9d9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f9d9-124">See Also</span></span>  
 [<span data-ttu-id="2f9d9-125">Configuración de las propiedades de acuerdos de reserva de X12 para valores de conjuntos de transacciones</span><span class="sxs-lookup"><span data-stu-id="2f9d9-125">Configuring X12 Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)