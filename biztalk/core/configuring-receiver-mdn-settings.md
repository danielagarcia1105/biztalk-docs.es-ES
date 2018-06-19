---
title: Configuración de MDN de receptor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae6431d-a2b9-4889-a29c-720e801a644e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dafe17a0ad357b840b31d8a10c67e1ae3cc1e415
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233380"
---
# <a name="configuring-receiver-mdn-settings"></a><span data-ttu-id="141fa-102">Configuración de MDN de receptor</span><span class="sxs-lookup"><span data-stu-id="141fa-102">Configuring Receiver MDN Settings</span></span>
<span data-ttu-id="141fa-103">Como parte de la configuración de MDN de receptor, se pueden especificar las propiedades que rigen la generación de MDN, en función de la cabecera del mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="141fa-103">As part of receiver MDN settings, you can specify the properties that govern MDN generation based on the AS2 message header.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="141fa-104">Ninguna propiedad se deshabilita en **entidad A -> B entidad** ficha de acuerdo unidireccional si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación para la entidad A. Sin embargo, se deshabilitan todas las propiedades en la misma página en la **parte B -> parte A** ficha si ha seleccionado la casilla de verificación al crear la entidad A.</span><span class="sxs-lookup"><span data-stu-id="141fa-104">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="141fa-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="141fa-105">Prerequisites</span></span>  
 <span data-ttu-id="141fa-106">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="141fa-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-receiver-mdn-settings"></a><span data-ttu-id="141fa-107">Para configurar el MDN de receptor</span><span class="sxs-lookup"><span data-stu-id="141fa-107">To configure receiver MDN settings</span></span>  
  
1.  <span data-ttu-id="141fa-108">Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md).</span><span class="sxs-lookup"><span data-stu-id="141fa-108">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="141fa-109">Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="141fa-109">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="141fa-110">En una ficha de acuerdo unidireccional, bajo **configuración de Host Local** sección, haga clic en **configuración de MDN de receptor**.</span><span class="sxs-lookup"><span data-stu-id="141fa-110">On a one-way agreement tab, under **Local Host Settings** section, click **Receiver MDN Settings**.</span></span>  
  
3.  <span data-ttu-id="141fa-111">Si no activó la **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad en el **validaciones** página, se puede elegir que la entidad que envía el MDN, firmar el MDN si generación del MDN está habilitada por la **Disposition-Notification-to** encabezado de AS2, pero la **Disposition-Notification-Options** encabezado no habilitar la firma.</span><span class="sxs-lookup"><span data-stu-id="141fa-111">If you did not check the **Use agreement settings for validation and MDN instead of message header** property in the **Validations** page, you can choose to have the party sending the MDN, sign the MDN if generation of the MDN is enabled by the **Disposition-Notification-to** AS2 header, but the **Disposition-Notification-Options** header does not enable signing.</span></span> <span data-ttu-id="141fa-112">Esto puede ocurrir si **Disposition-Notification-Options** no está establecida o está establecido en opcional.</span><span class="sxs-lookup"><span data-stu-id="141fa-112">This can occur if **Disposition-Notification-Options** is either not set or is set to optional.</span></span> <span data-ttu-id="141fa-113">Puede hacerlo haciendo clic en **firmar el MDN solicitado si el encabezado Disposition-Notification-Option no está predefinida o si el encabezado Signed-Receipt-Protocol está establecido en opcional**.</span><span class="sxs-lookup"><span data-stu-id="141fa-113">You can do so by clicking **Sign requested MDN if Disposition-Notification-Option header is not preset or if Signed-Receipt-Protocol header is set to optional**.</span></span>  
  
4.  <span data-ttu-id="141fa-114">Puede escribir un texto en el **texto de MDN** campo para que la entidad que envía el MDN lo agregue al mensaje MDN (en el campo Content-Description).</span><span class="sxs-lookup"><span data-stu-id="141fa-114">You can enter a text in the **MDN Text** field to have the party sending the MDN add it to the MDN message (under the Content-Description field).</span></span> <span data-ttu-id="141fa-115">Esta configuración es aplicable independientemente de si el MDN se ha generado en función de los encabezados de AS2 o de las propiedades del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="141fa-115">This setting is applicable irrespective of whether the MDN was generated based upon the AS2 headers or the agreement properties.</span></span>  
  
5.  <span data-ttu-id="141fa-116">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="141fa-116">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="141fa-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="141fa-117">See Also</span></span>  
 [<span data-ttu-id="141fa-118">Configuración del Host Local (AS2)</span><span class="sxs-lookup"><span data-stu-id="141fa-118">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)