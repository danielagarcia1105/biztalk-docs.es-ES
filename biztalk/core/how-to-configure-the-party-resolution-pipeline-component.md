---
title: Cómo configurar el componente de canalización de resolución de entidades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authenticating, Partner Management
- Party Resolution [pipeline component], configuring
- Partner Management, authenticating
- pipeline components, Party Resolution
ms.assetid: 0ebd30f7-3a6b-4457-8e30-80bf81fbd28d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0c78792cd7c61ed1297954625fbd7da5aedfa04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248220"
---
# <a name="how-to-configure-the-party-resolution-pipeline-component"></a><span data-ttu-id="32cdd-102">Cómo configurar el componente de canalización Resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="32cdd-102">How to Configure the Party Resolution Pipeline Component</span></span>
<span data-ttu-id="32cdd-103">El componente de canalización de resolución de entidades se utiliza para asignar el Id. de seguridad de usuario y el sujeto del certificado para el cliente a una entidad de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="32cdd-103">The Party Resolution pipeline component is used to map the user security ID and the certificate subject for the client to a BizTalk Server party.</span></span> <span data-ttu-id="32cdd-104">La asignación se utiliza para forzar la autenticación de las entidades que envían mensajes a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="32cdd-104">The mapping is used to enforce authentication of the parties who send messages to BizTalk Server.</span></span> <span data-ttu-id="32cdd-105">Para obtener más información acerca de la administración de socios comerciales, vea[cómo crear un acuerdo](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c).</span><span class="sxs-lookup"><span data-stu-id="32cdd-105">For more information about partner management, see[How to Create an Agreement](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32cdd-106">Para permitir que el componente de canalización de resolución de entidades valide a un usuario de Windows, se debe agregar el alias WindowsUser a una entidad.</span><span class="sxs-lookup"><span data-stu-id="32cdd-106">To enable the Party Resolution pipeline component to validate a Windows user, you must add the WindowsUser alias to a party.</span></span> <span data-ttu-id="32cdd-107">Para obtener más información, consulte [componente de canalización de resolución de entidad](../core/party-resolution-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="32cdd-107">For more information, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>  
  
### <a name="to-configure-the-properties-for-the-party-resolution-pipeline-component"></a><span data-ttu-id="32cdd-108">Para configurar las propiedades del componente de canalización de resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="32cdd-108">To configure the properties for the Party Resolution pipeline component</span></span>  
  
1.  <span data-ttu-id="32cdd-109">Arrastre el componente de canalización de resolución de entidades hasta la fase ResolveParty de una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="32cdd-109">Drag the Party Resolution pipeline component into the ResolveParty stage of a receive pipeline.</span></span>  
  
2.  <span data-ttu-id="32cdd-110">En la ventana Propiedades, en la **propiedades de componente de canalización** sección, realice lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="32cdd-110">In the Properties window, in the **Pipeline Component Properties** section, do the following.</span></span>  
  
    |<span data-ttu-id="32cdd-111">Use</span><span class="sxs-lookup"><span data-stu-id="32cdd-111">Use this</span></span>|<span data-ttu-id="32cdd-112">Para</span><span class="sxs-lookup"><span data-stu-id="32cdd-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="32cdd-113">**Resolver entidad mediante certificado**</span><span class="sxs-lookup"><span data-stu-id="32cdd-113">**Resolve Party By Certificate**</span></span>|<span data-ttu-id="32cdd-114">Establecido en **True** si desea habilitar la resolución de entidades en función de la huella digital del certificado de firma de la entidad desde la cual se reciben los mensajes.</span><span class="sxs-lookup"><span data-stu-id="32cdd-114">Set to **True** if you want to enable party resolution based on the thumbprint of the signature certificate from the party from where the messages are received.</span></span><br /><br /> <span data-ttu-id="32cdd-115">Valor predeterminado: **True**</span><span class="sxs-lookup"><span data-stu-id="32cdd-115">Default value: **True**</span></span>|  
    |<span data-ttu-id="32cdd-116">**Resolver entidad mediante SID**</span><span class="sxs-lookup"><span data-stu-id="32cdd-116">**Resolve Party By SID**</span></span>|<span data-ttu-id="32cdd-117">Establecido en **True** si desea habilitar la resolución de entidades basada en el identificador de seguridad (SID) de la cuenta del remitente.</span><span class="sxs-lookup"><span data-stu-id="32cdd-117">Set to **True** if you want to enable party resolution based on the security identifier (SID) of the sender account.</span></span><br /><br /> <span data-ttu-id="32cdd-118">Si ambas propiedades se establecen en **True**, **resolver entidad mediante certificado** propiedad tiene prioridad sobre la **resolver entidad mediante SID** propiedad, lo que significa que si el certificado como el SID están disponibles, se utiliza el sujeto del certificado.</span><span class="sxs-lookup"><span data-stu-id="32cdd-118">If both properties are set to **True**, the **Resolve Party By Certificate** property takes precedence over the **Resolve Party By SID** property, meaning that if both the certificate and the SID are available, the certificate subject is used.</span></span> <span data-ttu-id="32cdd-119">Si no se puede resolver la entidad utilizando el sujeto del certificado, el componente no regresa a la **resolver entidad mediante SID** propiedad y el valor predeterminado (s-1-5-7) se marca para **BTS. Sourcepartyid esta**.</span><span class="sxs-lookup"><span data-stu-id="32cdd-119">If the party cannot be resolved by using the certificate subject, the component does not fall back to the **Resolve Party By SID** property, and the default value (s-1-5-7) is stamped for **BTS.SourcePartyID**.</span></span><br /><br /> <span data-ttu-id="32cdd-120">Valor predeterminado: **True**</span><span class="sxs-lookup"><span data-stu-id="32cdd-120">Default value: **True**</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="32cdd-121">Si usa el adaptador de BizTalk para Message Queue y desea resolver la entidad basan en nombre de usuario, establezca **resolver entidad mediante certificado** a **False** y **resolver entidad mediante SID** a **True**.</span><span class="sxs-lookup"><span data-stu-id="32cdd-121">If you use the BizTalk Message Queuing adapter and want to resolve the party based on user name, set **Resolve Party By Certificate** to **False** and **Resolve Party By SID** to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32cdd-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="32cdd-122">See Also</span></span>  
 <span data-ttu-id="32cdd-123">[Componente de canalización de resolución de entidades](../core/party-resolution-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="32cdd-123">[Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md) </span></span>  
 <span data-ttu-id="32cdd-124">[Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="32cdd-124">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="32cdd-125">Resolución de entidades personalizadas (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="32cdd-125">Custom Party Resolution (BizTalk Server Sample)</span></span>](../core/custom-party-resolution-biztalk-server-sample.md)