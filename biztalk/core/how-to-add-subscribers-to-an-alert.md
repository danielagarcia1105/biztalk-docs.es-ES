---
title: Cómo agregar suscriptores a una alerta | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- subscriptions, subscribers
- subscriptions
- managing [BAM], adding alert subscribers
ms.assetid: c76a117d-4516-4f48-995c-7e018dbba755
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0174d5f37bc34b6c882d82cb58192ce9f1d634d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972621"
---
# <a name="how-to-add-subscribers-to-an-alert"></a><span data-ttu-id="cb0fe-102">Cómo agregar suscriptores a una alerta</span><span class="sxs-lookup"><span data-stu-id="cb0fe-102">How to Add Subscribers to an Alert</span></span>
<span data-ttu-id="cb0fe-103">Los administradores utilizan el **Agregar suscripción** comando para agregar un suscriptor a una alerta específica.</span><span class="sxs-lookup"><span data-stu-id="cb0fe-103">Administrators use the **add-subscription** command to add a subscriber to a specified alert.</span></span>  
  
### <a name="to-add-subscribers-to-an-alert"></a><span data-ttu-id="cb0fe-104">Para agregar suscriptores a una alerta</span><span class="sxs-lookup"><span data-stu-id="cb0fe-104">To add subscribers to an alert</span></span>  
  
1. <span data-ttu-id="cb0fe-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb0fe-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="cb0fe-106">Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="cb0fe-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="cb0fe-107">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="cb0fe-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="cb0fe-108">Tipo `bm add-subscription -View:<view name> -Alert:<alert name> -AccountName:<account name> -Type: [ File | Email ][ -Email:<e-mail address> ]`.</span><span class="sxs-lookup"><span data-stu-id="cb0fe-108">Type `bm add-subscription -View:<view name> -Alert:<alert name> -AccountName:<account name> -Type: [ File | Email ][ -Email:<e-mail address> ]`.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cb0fe-109">*Tipo* especifica el método de entrega que utiliza BAM para entregar la alerta.</span><span class="sxs-lookup"><span data-stu-id="cb0fe-109">*Type* specifies the delivery method which BAM uses to deliver the alert.</span></span> <span data-ttu-id="cb0fe-110">Si especifica un tipo de entrega de correo electrónico, deberá proporcionar una dirección de correo electrónico en la que se entregue la alerta.</span><span class="sxs-lookup"><span data-stu-id="cb0fe-110">If you specify a delivery type of e-mail you must supply an e-mail address to which the alert is delivered.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cb0fe-111">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="cb0fe-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="cb0fe-112">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="cb0fe-112">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb0fe-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb0fe-113">See Also</span></span>  
 <span data-ttu-id="cb0fe-114">[Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="cb0fe-114">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="cb0fe-115">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="cb0fe-115">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="cb0fe-116">Cómo quitar suscriptores de una alerta</span><span class="sxs-lookup"><span data-stu-id="cb0fe-116">How to Remove Subscribers from an Alert</span></span>](../core/how-to-remove-subscribers-from-an-alert.md)