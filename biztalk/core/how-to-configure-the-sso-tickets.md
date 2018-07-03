---
title: Cómo configurar los vales de SSO | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], configuring tickets
- SSO, tickets
- tickets [SSO], configuring
ms.assetid: 32f0384b-ac79-4cce-b3f5-f4f8a73a673a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edec81ab1fa64ce7b4523771bb2c69b39c00bdfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018762"
---
# <a name="how-to-configure-the-sso-tickets"></a><span data-ttu-id="25bdd-102">Cómo configurar los vales de SSO</span><span class="sxs-lookup"><span data-stu-id="25bdd-102">How to Configure the SSO Tickets</span></span>
<span data-ttu-id="25bdd-103">Se puede utilizar el Complemento MMC o la línea de comandos para controlar el comportamiento de los vales en la totalidad del sistema de inicio de sesión único; lo anterior incluye la posibilidad de permitir vales y la exigencia de que el sistema los valide.</span><span class="sxs-lookup"><span data-stu-id="25bdd-103">You can use the MMC Snap-In or the command line to control ticket behavior for the entire Single Sign-On system, including whether to allow tickets, and whether the system must validate the tickets.</span></span>  
  
 <span data-ttu-id="25bdd-104">Se pueden utilizar las opciones Sí, No, Activado o Desactivado para indicar si se permiten los vales y/o si se validan.</span><span class="sxs-lookup"><span data-stu-id="25bdd-104">You can use Yes, No, On, or Off to indicate whether to allow and/or validate tickets.</span></span> <span data-ttu-id="25bdd-105">El uso de mayúsculas y minúsculas en estas palabras carece de importancia y se deben utilizar independientemente de la configuración del idioma.</span><span class="sxs-lookup"><span data-stu-id="25bdd-105">These words are case independent, and must be used regardless of your language settings.</span></span>  
  
 <span data-ttu-id="25bdd-106">Si la característica Administración de SSO se encuentra instalado en un equipo remoto, se puede llevar a cabo una operación IssueTicket remota.</span><span class="sxs-lookup"><span data-stu-id="25bdd-106">If you have the SSO Administration feature installed on a remote computer, remote IssueTicket operation can be performed.</span></span> <span data-ttu-id="25bdd-107">Tenga en cuenta que se cifra todo el tráfico entre el módulo Administración de SSO y el módulo Tiempo de ejecución (servicio ENTSSO).</span><span class="sxs-lookup"><span data-stu-id="25bdd-107">Note that all traffic between the SSO Administration module and the Runtime module (ENTSSO service) is encrypted.</span></span>  
  
 <span data-ttu-id="25bdd-108">Al utilizar la utilidad de línea de comandos, ssomanage.exe, se puede especificar el tiempo de espera de vale en el nivel de aplicación afiliada únicamente al llevar a cabo una actualización de la aplicación, no a la hora de la creación.</span><span class="sxs-lookup"><span data-stu-id="25bdd-108">Using the command line utility, ssomanage.exe, you can specify the ticket timeout at the Affiliate Application level only when an update of the Application is performed,  not at creation time.</span></span>  
  
 <span data-ttu-id="25bdd-109">Sólo un administrador de SSO puede configurar vales en el nivel de sistema de SSO y en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="25bdd-109">Only an SSO Administrator can configure tickets at the SSO System level and at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="25bdd-110">Si se deshabilita la compra de vales en el nivel del sistema, tampoco se podrá utilizar en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="25bdd-110">If ticketing is disabled at the system level, it cannot be used at the Affiliate Application level either.</span></span> <span data-ttu-id="25bdd-111">Es posible habilitar los vales en el nivel de sistema y deshabilitarlos en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="25bdd-111">It is possible to enable tickets at the system level and disable it at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="25bdd-112">Si se habilita la validación en el nivel de sistema, también se requiere la validación de vales en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="25bdd-112">If validation is enabled at the system level, validation of tickets are required at the Affiliate Application level as well.</span></span> <span data-ttu-id="25bdd-113">Es posible deshabilitar la validación en el nivel de sistema y habilitarla en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="25bdd-113">It is possible to disable validation at the system level and enable it at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="25bdd-114">Si el tiempo de espera de vales se especifica en el nivel de sistema y en el de aplicación afiliada, aquel que se especifique en el nivel de aplicación afiliada se utilizará para determinar la hora de expiración de vales.</span><span class="sxs-lookup"><span data-stu-id="25bdd-114">If Ticket timeout is specified both at the System level and the Affiliate Application level, the one specified at the Affiliate Application level is used to determine the ticket expiry time.</span></span>  
  
 <span data-ttu-id="25bdd-115">Para obtener más información acerca de vales y validación de vales, consulte [vales de SSO](../core/sso-tickets.md).</span><span class="sxs-lookup"><span data-stu-id="25bdd-115">For more information about tickets and tickets validation, see [SSO Tickets](../core/sso-tickets.md).</span></span>  
  
### <a name="to-configure-the-enterprise-single-sign-on-tickets-using-the-mmc-snap-in-for-the-affiliate-application"></a><span data-ttu-id="25bdd-116">Para configurar los vales de inicio de sesión único empresarial utilizando el Complemento MMC para la aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="25bdd-116">To configure the Enterprise Single Sign-On tickets using the MMC Snap-In for the Affiliate Application</span></span>  
  
1.  <span data-ttu-id="25bdd-117">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="25bdd-117">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="25bdd-118">En el panel de ámbito del complemento MMC de ENTSSO, expanda el **aplicaciones afiliadas** nodo.</span><span class="sxs-lookup"><span data-stu-id="25bdd-118">In the scope pane of the ENTSSO MMC Snap-In, expand the **Affiliate Applications** node.</span></span>  
  
3.  <span data-ttu-id="25bdd-119">Haga clic en **aplicación afiliada**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="25bdd-119">Right-click **Affiliate Application**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="25bdd-120">Haga clic en el **opciones** ficha.</span><span class="sxs-lookup"><span data-stu-id="25bdd-120">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="25bdd-121">Seleccione **permitir vales** y configure el tiempo de espera de vale según corresponda.</span><span class="sxs-lookup"><span data-stu-id="25bdd-121">Select **Allow Tickets** and configure the ticket timeout as appropriate.</span></span>  
  
### <a name="to-configure-the-enterprise-single-sign-on-system-level-tickets-using-the-command-line"></a><span data-ttu-id="25bdd-122">Para configurar los vales de nivel de inicio de sesión único empresarial mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="25bdd-122">To configure the Enterprise Single Sign-On system-level tickets using the command line</span></span>  
  
1. <span data-ttu-id="25bdd-123">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="25bdd-123">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="25bdd-124">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="25bdd-124">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="25bdd-125">El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="25bdd-125">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="25bdd-126">Tipo ** ssomanage – vales \<sí/no de permiten\> *\<validar sí/no\>**<em>, donde *\<sí/no de permiten\></em>  indica si se permitirán vales o no, y *\<validar sí/no\>* indica si los vales necesitará que se valida una vez canjeados.</span><span class="sxs-lookup"><span data-stu-id="25bdd-126">Type **ssomanage –tickets \<allowed yes/no\> *\<validate yes/no\>**<em>, where *\<allowed yes/no\></em> indicates whether tickets will be allowed or not, and *\<validate yes/no\>* indicates whether tickets will need to be validated after they are redeemed.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="25bdd-127">Se pueden utilizar las opciones sí, no, activado o desactivado para indicar si se permiten los vales y/o si se validan.</span><span class="sxs-lookup"><span data-stu-id="25bdd-127">You can use yes, no, on, or off to indicate whether to allow and/or validate tickets.</span></span> <span data-ttu-id="25bdd-128">El uso de mayúsculas y minúsculas en estas palabras carece de importancia y se deben utilizar independientemente de la configuración del idioma.</span><span class="sxs-lookup"><span data-stu-id="25bdd-128">These words are case independent, and must be used regardless of your language settings.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="25bdd-129">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="25bdd-129">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25bdd-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="25bdd-130">See Also</span></span>  
 <span data-ttu-id="25bdd-131">[Descripción de SSO](../core/understanding-sso.md) </span><span class="sxs-lookup"><span data-stu-id="25bdd-131">[Understanding SSO](../core/understanding-sso.md) </span></span>  
 [<span data-ttu-id="25bdd-132">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="25bdd-132">Using SSO</span></span>](../core/using-sso.md)