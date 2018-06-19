---
title: 'Paso 3: Modificar el proceso de la interfaz de socio comercial | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, PIPs
- PIPs, modifying
- loopback tutorial, modifying PIPs
ms.assetid: 4d03c598-8ed4-4135-9748-ede101997fd0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b6300c12e7bc28de0dc81af9eae23699338ed3d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965074"
---
# <a name="step-3-edit-the-partner-interface-process"></a><span data-ttu-id="b649b-102">Paso 3: Modificar el proceso de la interfaz de socio comercial</span><span class="sxs-lookup"><span data-stu-id="b649b-102">Step 3: Edit the Partner Interface Process</span></span>
<span data-ttu-id="b649b-103">En este paso, va a editar las opciones de configuración de proceso de interfaz de socio (PIP) para deshabilitar el transporte seguro si no tiene un certificado de capa de Sockets seguros (SSL) configurado en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b649b-103">In this step, you edit the Partner Interface Process (PIP) configuration settings to disable secure transport if you do not have a Secure Sockets Layer (SSL) certificate configured in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® Internet Information Services (IIS).</span></span> <span data-ttu-id="b649b-104">Dado que el escenario de bucle invertido no es compatible con la firma para los mensajes entrantes y salientes, debe cambiar la configuración predeterminada para continuar con el tutorial.</span><span class="sxs-lookup"><span data-stu-id="b649b-104">Because the loopback scenario does not support signing for both incoming and outgoing messages, you must change the default settings to continue with the tutorial.</span></span> <span data-ttu-id="b649b-105">Modifique el PIP STD_0C1_R01.02.</span><span class="sxs-lookup"><span data-stu-id="b649b-105">You modify the STD_0C1_R01.02 PIP.</span></span>  
  
### <a name="to-edit-the-std0c1r0102-pip"></a><span data-ttu-id="b649b-106">Para editar el PIP STD_0C1_R01.02</span><span class="sxs-lookup"><span data-stu-id="b649b-106">To edit the STD_0C1_R01.02 PIP</span></span>  
  
1.  <span data-ttu-id="b649b-107">En el  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Management Console, expanda **BizTalk \<versión\> Acelerador para RosettaNet**, haga clic en **valores de configuración de proceso** , haga clic en **STD_0C1_R01.02**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b649b-107">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand **BizTalk \<version\> Accelerator for RosettaNet**, click **Process Configuration Settings**, right-click **STD_0C1_R01.02**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b649b-108">En el cuadro de diálogo STD_0C1_R01.02Properties, en la **actividad** pestaña, establezca el **se requiere de transporte seguro** opción `False`.</span><span class="sxs-lookup"><span data-stu-id="b649b-108">In the STD_0C1_R01.02Properties dialog box, on the **Activity** tab, set the **Is Secure Transport Required** option to `False`.</span></span> <span data-ttu-id="b649b-109">Realice este paso solo si no tiene un certificado SSL en el servidor Web de IIS.</span><span class="sxs-lookup"><span data-stu-id="b649b-109">Perform this step only if you do not have a SSL certificate on your IIS Web server.</span></span>  
  
3.  <span data-ttu-id="b649b-110">Establecer el **sin repudio necesario** a `False`, establezca **se necesita autorización** a `False`, establezca **sin repudio del origen y del contenido** a `False`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b649b-110">Set the **Non-Repudiation Required** to `False`, set **Is Authorization Required** to `False`, set **Non-Repudiation of Origin and Content** to `False`, and then click **OK**.</span></span>  
  
     <span data-ttu-id="b649b-111">Esto deshabilita sin repudio y el uso de certificados para firmar mensajes.</span><span class="sxs-lookup"><span data-stu-id="b649b-111">This disables non-repudiation and the use of certificates for signing messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b649b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b649b-112">See Also</span></span>  
 <span data-ttu-id="b649b-113">[Paso 4: Crear un acuerdo comercial](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="b649b-113">[Step 4: Create a Trade Agreement](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md) </span></span>  
 [<span data-ttu-id="b649b-114">Propiedades de autorización y no rechazo</span><span class="sxs-lookup"><span data-stu-id="b649b-114">Authorization and Non-Repudiation Properties</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)