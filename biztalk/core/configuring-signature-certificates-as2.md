---
title: "Configuración de certificados de firma (AS2) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8539e210-1656-4fff-b026-36b81689061f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32a52962976c2db62de902906f53f5c270e2c7c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-signature-certificates-as2"></a><span data-ttu-id="2eeb9-102">Configuración de certificados de firma (AS2)</span><span class="sxs-lookup"><span data-stu-id="2eeb9-102">Configuring Signature Certificates (AS2)</span></span>
<span data-ttu-id="2eeb9-103">Como parte de la configuración de esta página, puede especificar los certificados que se deben usar para firmar todos los mensajes salientes y el MDN que se resuelve en este acuerdo.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-103">As part of the settings on this page, you can specify the certificates to be used for signing all outgoing messages and MDN that resolve to this agreement.</span></span> <span data-ttu-id="2eeb9-104">La configuración de esta página invalida la configuración de certificado proporcionada en las propiedades del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-104">The settings on this page override the certificate settings provided as part of the BizTalk Group properties.</span></span> <span data-ttu-id="2eeb9-105">Para obtener más información sobre cómo se usan certificados, consulte [configurar certificados para AS2](../core/configuring-certificates-for-as2.md).</span><span class="sxs-lookup"><span data-stu-id="2eeb9-105">For more information on how certificates are used, see [Configuring Certificates for AS2](../core/configuring-certificates-for-as2.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2eeb9-106">Ninguna propiedad se deshabilita en esta página, incluso si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-106">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2eeb9-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2eeb9-107">Prerequisites</span></span>  
 <span data-ttu-id="2eeb9-108">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2eeb9-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-agreement-level-signature-certificate"></a><span data-ttu-id="2eeb9-109">Para configurar certificados de firma de nivel de acuerdo</span><span class="sxs-lookup"><span data-stu-id="2eeb9-109">To configure agreement-level signature certificate</span></span>  
  
1.  <span data-ttu-id="2eeb9-110">Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md).</span><span class="sxs-lookup"><span data-stu-id="2eeb9-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="2eeb9-111">Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="2eeb9-112">En una ficha de acuerdo unidireccional, haga clic en **certificados de firma de**.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-112">On a one-way agreement tab, click **Signature Certificates**.</span></span>  
  
3.  <span data-ttu-id="2eeb9-113">Seleccione el **certificado de firma de grupo de invalidación** casilla de verificación para usar el certificado proporcionado en esta página para firmar mensajes AS2 salientes y MDN.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-113">Select the **Override group signing certificate** check box to use the certificate provided in this page for signing outgoing AS2 messages and MDN.</span></span>  
  
4.  <span data-ttu-id="2eeb9-114">Haga clic en **examinar** para mostrar la **Seleccionar certificado** cuadro de diálogo, donde podrá seleccionar el certificado de firma que se aplicará a los mensajes transmitidos por esta entidad.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-114">Click **Browse** to display the **Select Certificate** dialog box, where you select the signature certificate to apply to messages transmitted by this party.</span></span>  
  
5.  <span data-ttu-id="2eeb9-115">El **nombre común** cuadro de texto muestra una descripción del certificado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-115">The **Common Name** text box displays a description of the selected certificate.</span></span>  
  
6.  <span data-ttu-id="2eeb9-116">El **huella digital** cuadro de texto muestra la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-116">The **Thumbprint** text box displays the thumbprint of certificate.</span></span> <span data-ttu-id="2eeb9-117">La huella digital del certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal (un número entre 0 y 9) o una letra de la A F.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-117">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit (a number from 0 through 9 or a letter from A through F).</span></span>  
  
7.  <span data-ttu-id="2eeb9-118">Haga clic en **quitar certificado** para quitar el certificado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-118">Click **Remove Certificate** to remove the selected certificate.</span></span>  
  
8.  <span data-ttu-id="2eeb9-119">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-119">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eeb9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2eeb9-120">See Also</span></span>  
 [<span data-ttu-id="2eeb9-121">Configurar propiedades del acuerdo de AS2</span><span class="sxs-lookup"><span data-stu-id="2eeb9-121">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)