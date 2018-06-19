---
title: Configuración de identificadores (AS2) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29f12696-8257-4664-8e61-292678e98b6b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1f4c8ddde24c32f93d003f778b9359d70e87170
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007445"
---
# <a name="configuring-identifiers-as2"></a><span data-ttu-id="23255-102">Configuración de identificadores (AS2)</span><span class="sxs-lookup"><span data-stu-id="23255-102">Configuring Identifiers (AS2)</span></span>
<span data-ttu-id="23255-103">En el acuerdo de socio, debe especificar las entidades de remitente y receptor.</span><span class="sxs-lookup"><span data-stu-id="23255-103">In the partner agreement, you must specify the sender and receiver parties.</span></span> <span data-ttu-id="23255-104">Estos valores también se usan para la resolución de acuerdo para los mensajes entrantes o salientes.</span><span class="sxs-lookup"><span data-stu-id="23255-104">These values are also used for agreement resolution for the inbound or outbound messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="23255-105">Las propiedades siguientes están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="23255-105">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  -   <span data-ttu-id="23255-106">**AS2To** en **resoluciones de acuerdos adicionales** sección.</span><span class="sxs-lookup"><span data-stu-id="23255-106">**AS2To** under **Additional Agreement Resolvers** section.</span></span>  
>   
>  <span data-ttu-id="23255-107">Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad.</span><span class="sxs-lookup"><span data-stu-id="23255-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="23255-108">Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.</span><span class="sxs-lookup"><span data-stu-id="23255-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="23255-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="23255-109">Prerequisites</span></span>  
 <span data-ttu-id="23255-110">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23255-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-identifier-properties"></a><span data-ttu-id="23255-111">Procedimiento para configurar las propiedades de identificador</span><span class="sxs-lookup"><span data-stu-id="23255-111">To configure the identifier properties</span></span>  
  
1.  <span data-ttu-id="23255-112">Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md).</span><span class="sxs-lookup"><span data-stu-id="23255-112">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="23255-113">Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="23255-113">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="23255-114">En una ficha de acuerdo unidireccional, haga clic en **identificadores**.</span><span class="sxs-lookup"><span data-stu-id="23255-114">On a one-way agreement tab, click **Identifiers**.</span></span>  
  
3.  <span data-ttu-id="23255-115">En el **AS2-de** página, especifique el nombre del socio comercial que envía el mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="23255-115">In the **AS2-From** page, specify the name of the trading partner sending the AS2 message.</span></span>  
  
4.  <span data-ttu-id="23255-116">En el **AS2-para** página, especifique el nombre del socio comercial que recibe el mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="23255-116">In the **AS2-To** page, specify the name of the trading partner receiving the AS2 message.</span></span>  
  
5.  <span data-ttu-id="23255-117">En el **resoluciones de acuerdos adicionales** sección, para la **AS2To** propiedad, escriba un alias adicional para el socio que recibe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="23255-117">Under the **Additional Agreement Resolvers** section, for the **AS2To** property, enter an additional alias for the partner that receives the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23255-118">Esta propiedad es opcional.</span><span class="sxs-lookup"><span data-stu-id="23255-118">This property is optional.</span></span> <span data-ttu-id="23255-119">Esta propiedad está disponible para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="23255-119">This property is available for backward compatibility.</span></span> <span data-ttu-id="23255-120">Cuando se migra una definición de la entidad de BizTalk Server 2006 R2 o BizTalk Server 2009 a BizTalk Server, el nombre de la entidad en las versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se incluye como un valor para esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="23255-120">When a party definition is migrated from BizTalk Server 2006 R2 or BizTalk Server 2009 to BizTalk Server, the name of the party in the previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is included as a value for this property.</span></span> <span data-ttu-id="23255-121">Esto garantiza que se produce la resolución del acuerdo y las aplicaciones existentes y definiciones de socio pueden utilizarse con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="23255-121">This ensures that the agreement resolution happens and the existing applications and partner definitions can be used with BizTalk Server.</span></span>  
  
6.  <span data-ttu-id="23255-122">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="23255-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23255-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="23255-123">See Also</span></span>  
 [<span data-ttu-id="23255-124">Configuración de las propiedades de acuerdo AS2</span><span class="sxs-lookup"><span data-stu-id="23255-124">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)