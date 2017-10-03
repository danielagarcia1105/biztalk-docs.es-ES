---
title: "Cómo configurar certificados para la resolución de entidades | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 060101c1-14f3-4600-a18e-48a160d59bca
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 153c8ccce1fafbe32c51b1c048fad4081f5b0b0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-certificates-for-party-resolution"></a><span data-ttu-id="9d7b2-102">Cómo configurar certificados para la resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="9d7b2-102">How to Configure Certificates for Party Resolution</span></span>
<span data-ttu-id="9d7b2-103">Al usar el Explorador de BizTalk para configurar una entidad, puede configurar la entidad para que la entidad se resuelve mediante la firma digital.</span><span class="sxs-lookup"><span data-stu-id="9d7b2-103">When you use BizTalk Explorer to configure a party, you can configure the party so that the party is resolved by using its digital signature.</span></span> <span data-ttu-id="9d7b2-104">Si configura la entidad de esta manera, cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje, usará el certificado de clave pública para determinar quién envió el mensaje y para resolver el remitente para una entidad conocida en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="9d7b2-104">If you configure the party this way, when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a message, it will use the public key certificate to determine who sent the message, and to resolve the sender to a known party in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9d7b2-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9d7b2-105">Prerequisites</span></span>  
 <span data-ttu-id="9d7b2-106">Para llevar a cabo el procedimiento de este tema, debe iniciar sesión como un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="9d7b2-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-party-resolution-to-use-a-certificate"></a><span data-ttu-id="9d7b2-107">Para configurar la resolución de entidades para utilizar un certificado</span><span class="sxs-lookup"><span data-stu-id="9d7b2-107">To configure party resolution to use a certificate</span></span>  
  
1.  <span data-ttu-id="9d7b2-108">Abra la **propiedades de la entidad** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9d7b2-108">Open the **Party Properties** dialog box.</span></span>  
  
2.  <span data-ttu-id="9d7b2-109">Haga clic en el **certificado** ficha y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="9d7b2-109">Click the **Certificate** tab, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="9d7b2-110">Seleccione un certificado.</span><span class="sxs-lookup"><span data-stu-id="9d7b2-110">Select a certificate.</span></span>  
  
4.  <span data-ttu-id="9d7b2-111">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9d7b2-111">Click **OK**.</span></span>