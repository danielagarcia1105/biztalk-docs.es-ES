---
title: Configuración de Host Local generales (AS2) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 980daac2-8387-44cc-ae55-38639f759668
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de5e5c076e6b245e4a662f8132d027e927df6142
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233820"
---
# <a name="configuring-general-local-host-settings-as2"></a><span data-ttu-id="6292d-102">Configuración de las opciones de host local generales (AS2)</span><span class="sxs-lookup"><span data-stu-id="6292d-102">Configuring General Local Host Settings (AS2)</span></span>
<span data-ttu-id="6292d-103">Como parte de la configuración general del host local, puede especificar el tipo de contenido de los mensajes AS2 y si el nombre de archivo se conserva como parte del encabezado de mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="6292d-103">As part of the local host general settings, you can specify the content type of the AS2 messages and whether the file name is preserved as part of the AS2 message header.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6292d-104">Todas las propiedades se deshabilitan en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="6292d-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="6292d-105">Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad.</span><span class="sxs-lookup"><span data-stu-id="6292d-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="6292d-106">Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.</span><span class="sxs-lookup"><span data-stu-id="6292d-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6292d-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6292d-107">Prerequisites</span></span>  
 <span data-ttu-id="6292d-108">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6292d-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-general-settings"></a><span data-ttu-id="6292d-109">Para configurar los parámetros generales</span><span class="sxs-lookup"><span data-stu-id="6292d-109">To configure the general settings</span></span>  
  
1.  <span data-ttu-id="6292d-110">Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md).</span><span class="sxs-lookup"><span data-stu-id="6292d-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="6292d-111">Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6292d-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6292d-112">En una ficha de acuerdo unidireccional, bajo **configuración de Host Local** sección, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="6292d-112">On a one-way agreement tab, under **Local Host Settings** section, click **General**.</span></span>  
  
3.  <span data-ttu-id="6292d-113">Seleccione el **Comprobar lista de revocación de certificados antes de enviar el mensaje** casilla de verificación para determinar si el certificado que se usará en la firma de mensajes salientes se ha incluido en la lista de revocación de certificados, que indica se ha revocado dicho TI, o si se ha superado la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="6292d-113">Select the **Check Certification Revocation List before sending the message** check box to determine whether the certificate to be used in signing an outgoing messages has been included in the Certification Revocation List, indicating that it has been revoked, or whether the expiration date has passed.</span></span> <span data-ttu-id="6292d-114">Si es así, BizTalk Server no cifrará el mensaje sino que lo suspenderá.</span><span class="sxs-lookup"><span data-stu-id="6292d-114">If so, BizTalk Server will not encrypt the message, but will suspend it.</span></span> <span data-ttu-id="6292d-115">Si esta propiedad está desactivada, BizTalk Server no llevará a cabo esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="6292d-115">If this property is cleared, BizTalk Server will not perform this check.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6292d-116">Existe una latencia relacionada con la recuperación de la lista de revocaciones de certificados y con la búsqueda en ella.</span><span class="sxs-lookup"><span data-stu-id="6292d-116">There is a latency involved with retrieving and searching the certificate revocation list.</span></span>  
  
4.  <span data-ttu-id="6292d-117">Para **tipo de contenido predeterminado**, seleccione el tipo de contenido predeterminado que se debe utilizar la entidad para un mensaje AS2 saliente.</span><span class="sxs-lookup"><span data-stu-id="6292d-117">For **Default content type**, select the default content type that the party must use for an outgoing AS2 message.</span></span> <span data-ttu-id="6292d-118">Si el `ContentType` propiedad se establece en el contexto de una parte del cuerpo de mensaje, que configuración se usa para generar el mensaje saliente; en caso contrario, el valor de esta **tipo de contenido predeterminado** se utiliza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6292d-118">If the `ContentType` property is set in the context for a message body part, that setting is used to generate the outgoing message; otherwise, the value of this **Default content type** property is used.</span></span>  
  
5.  <span data-ttu-id="6292d-119">Seleccione el **transmitir el nombre de archivo en un encabezado MIME** casilla de verificación para enviar un nombre de archivo como parte del encabezado MIME para el mensaje AS2 saliente.</span><span class="sxs-lookup"><span data-stu-id="6292d-119">Select the **Transmit file name in MIME header** check box to send a file name as part of the MIME header for the outbound AS2 message.</span></span> <span data-ttu-id="6292d-120">Para especificar el nombre de archivo, seleccione **especificar nombre de archivo** o **tiene sistema generar nombre de archivo**.</span><span class="sxs-lookup"><span data-stu-id="6292d-120">To specify the file name, select **Specify file name** or **Have system generate file name**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6292d-121">Seleccionar **tiene sistema generar nombre de archivo** generará un nuevo valor GUID como el nombre de archivo de datos adjuntos enviados en el mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="6292d-121">Selecting **Have system generate file name** will generate a new GUID value as the file name of each attachment sent in the AS2 message.</span></span>  
  
6.  <span data-ttu-id="6292d-122">Si seleccionó **especificar nombre de archivo**, escribir una propiedad de contexto o el valor de cadena en el **especificar nombre de archivo** campo.</span><span class="sxs-lookup"><span data-stu-id="6292d-122">If you selected **Specify file name**, enter a string value or context property in the **Specify file name** field.</span></span> <span data-ttu-id="6292d-123">También puede habilitar **suspender mensaje si no encuentra la propiedad de contexto (%Property%))** para suspender el mensaje si la propiedad de contexto seleccionado no existe para el mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="6292d-123">You can also enable **Suspend message if context property (e.g. %property%) not found** to suspend the message if the selected context property does not exist for the outbound message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6292d-124">Para especificar una propiedad de contexto, encierre el nombre de propiedad entre caracteres %.</span><span class="sxs-lookup"><span data-stu-id="6292d-124">To specify a context-property, enclose the property name with the % character.</span></span> <span data-ttu-id="6292d-125">Por ejemplo, `%FILE.ReceivedFileName%`.</span><span class="sxs-lookup"><span data-stu-id="6292d-125">For example, `%FILE.ReceivedFileName%`.</span></span>  
  
7.  <span data-ttu-id="6292d-126">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6292d-126">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6292d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6292d-127">See Also</span></span>  
 [<span data-ttu-id="6292d-128">Configuración del Host Local (AS2)</span><span class="sxs-lookup"><span data-stu-id="6292d-128">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)