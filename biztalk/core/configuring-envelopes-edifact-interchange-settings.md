---
title: "Configuración de sobres (configuración de intercambio EDIFACT) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 501ccc5f-e21c-4c36-9509-217d5b3ba21f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 531b559e690fae5369298a90cd372edcae79db57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-envelopes-edifact-interchange-settings"></a><span data-ttu-id="6b9d6-102">Configuración de sobres (configuración de intercambio de EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="6b9d6-102">Configuring Envelopes (EDIFACT-Interchange Settings)</span></span>
<span data-ttu-id="6b9d6-103">Esta sección proporciona instrucciones acerca de cómo configurar el sobre para mensajes EDIFACT salientes.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-103">This section provides instructions on how to configure the envelope for outgoing EDIFACT messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b9d6-104">Todas las propiedades se deshabilitan en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="6b9d6-105">Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="6b9d6-106">Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6b9d6-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6b9d6-107">Prerequisites</span></span>  
 <span data-ttu-id="6b9d6-108">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b9d6-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-interchange-envelope"></a><span data-ttu-id="6b9d6-109">Para configurar el sobre de intercambio</span><span class="sxs-lookup"><span data-stu-id="6b9d6-109">To configure the interchange envelope</span></span>  
  
1.  <span data-ttu-id="6b9d6-110">Crear un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md).</span><span class="sxs-lookup"><span data-stu-id="6b9d6-110">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="6b9d6-111">Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-111">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6b9d6-112">En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **sobres**.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-112">On a one-way agreement tab, under **Interchange Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="6b9d6-113">Para **(UNB8) código de prioridad de procesamiento**, escriba un valor con un carácter como mínimo y un máximo de un carácter alfabético.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-113">For **Processing priority code (UNB8)**, enter an alphabetical value with a minimum of one character and a maximum of one character.</span></span> <span data-ttu-id="6b9d6-114">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-114">This is an optional field.</span></span>  
  
4.  <span data-ttu-id="6b9d6-115">Para **acuerdo de comunicaciones (UNB10)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 35 caracteres.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-115">For **Communication agreement (UNB10)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="6b9d6-116">Este campo es opcional</span><span class="sxs-lookup"><span data-stu-id="6b9d6-116">This is an optional field</span></span>  
  
5.  <span data-ttu-id="6b9d6-117">Seleccione **indicador de prueba (UNB11)** para indicar que el intercambio generado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] son datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-117">Select **Test indicator (UNB11)** to indicate that the interchange generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is test data.</span></span>  
  
6.  <span data-ttu-id="6b9d6-118">Seleccione **aplicar segmento UNA (notificación del servicio)** para generar un segmento UNA para el intercambio que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-118">Select **Apply UNA segment (String service advice)** to generate a UNA segment for the interchange to be sent.</span></span> <span data-ttu-id="6b9d6-119">Si se activa esta opción, a continuación, **UNA6** no puede estar vacío y **el sufijo una 6** no puede ser **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-119">If this option is checked, then **UNA6** cannot be empty and **UNA 6 Suffix** cannot be **None**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b9d6-120">Especifique **UNA6** y **sufijo UNA6** en el **juego de caracteres y separadores** tal y como se describe en la página [configurar el juego de caracteres y separadores (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).</span><span class="sxs-lookup"><span data-stu-id="6b9d6-120">You specify **UNA6** and **UNA6 Suffix** in the **Charset and Separators** page as described in [Configuring Charset and Separators (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).</span></span>  
  
7.  <span data-ttu-id="6b9d6-121">Seleccione **aplicar segmentos UNG (encabezado de grupo funcional)** para crear segmentos de agrupación en el encabezado de grupo funcional en los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-121">Select **Apply UNG segments (Functional group header)** to create grouping segments in the functional group header in outgoing messages.</span></span>  
  
8.  <span data-ttu-id="6b9d6-122">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6b9d6-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b9d6-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b9d6-123">See Also</span></span>  
 [<span data-ttu-id="6b9d6-124">Configuración de intercambio (EDIFACT).</span><span class="sxs-lookup"><span data-stu-id="6b9d6-124">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)