---
title: Cómo crear un adaptador de sincronización de contraseña | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caa5bd13-efd9-4544-b5df-17d01c6ac5d8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c47381cc1ed71788673602c1db7eec5b5ac049ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249372"
---
# <a name="how-to-create-a-password-sync-adapter"></a><span data-ttu-id="f2940-102">Cómo crear un adaptador de sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="f2940-102">How to Create a Password Sync Adapter</span></span>
<span data-ttu-id="f2940-103">Un adaptador de sincronización de contraseñas (PS) es una aplicación que utiliza el componente Aplicación auxiliar de sincronización de contraseñas para pasar notificaciones a inicio de sesión único empresarial (SSO) y recibirlas de éste.</span><span class="sxs-lookup"><span data-stu-id="f2940-103">A password sync (PS) adapter is an application that uses the Password Sync Helper component to pass notifications to and from Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="f2940-104">Tenga en cuenta que aunque el componente Aplicación auxiliar de PS exponga una interfaz COM y .NET Framework, el adaptador no tiene por qué ser un componente COM.</span><span class="sxs-lookup"><span data-stu-id="f2940-104">Note that although the PS Helper component exposes a COM and a .NET Framework interface, your adapter does not necessarily have to be a COM component.</span></span> <span data-ttu-id="f2940-105">Puede diseñar el adaptador como un proceso independiente, una aplicación COM+ o un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="f2940-105">You can design your adapter as a stand-alone process, a COM+ application, or a Windows service.</span></span>  
  
### <a name="to-create-a-password-sync-adapter"></a><span data-ttu-id="f2940-106">Para crear un adaptador de sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="f2940-106">To create a password sync adapter</span></span>  
  
1.  <span data-ttu-id="f2940-107">Informar al servicio de inicio de sesión único empresarial (ENTSSO) que el proveedor está utilizando active `ISSOPSWrapper.InitializeAdapter`.</span><span class="sxs-lookup"><span data-stu-id="f2940-107">Inform Enterprise Single Sign-On service (ENTSSO) that your provider is active using `ISSOPSWrapper.InitializeAdapter`.</span></span>  
  
     <span data-ttu-id="f2940-108">`InitializeAdapter`informa a ENTSSO que se encuentra activado un proveedor, normalmente el mismo proveedor que realiza la llamada, y, por lo tanto, estará enviando actualizaciones de contraseñas hacia y desde el sistema.</span><span class="sxs-lookup"><span data-stu-id="f2940-108">`InitializeAdapter` informs ENTSSO that a provider, usually the same provider that is making the call, is currently turned on, and therefore will be communicating password updates to and from the system.</span></span> <span data-ttu-id="f2940-109">También puede usar `InitializeAdapter` para activar otros recursos, como adaptadores de grupo.</span><span class="sxs-lookup"><span data-stu-id="f2940-109">You can also use `InitializeAdapter` to activate other resources such as group adapters.</span></span>  
  
2.  <span data-ttu-id="f2940-110">Enviar actualizaciones de contraseñas a ENTSSO mediante `ISSOPSWrapper.SendNotification`.</span><span class="sxs-lookup"><span data-stu-id="f2940-110">Send password updates to ENTSSO by using `ISSOPSWrapper.SendNotification`.</span></span>  
  
     <span data-ttu-id="f2940-111">Debe determinar cómo recibe las actualizaciones de contraseña de su sistema ajeno a Windows.</span><span class="sxs-lookup"><span data-stu-id="f2940-111">You must determine how you receive password updates from your non-Windows system.</span></span> <span data-ttu-id="f2940-112">Después de recibir la actualización, puede pasar la información a ENTSSO mediante `SendNotification`.</span><span class="sxs-lookup"><span data-stu-id="f2940-112">After you receive the update, you can pass the information on to ENTSSO using `SendNotification`.</span></span> <span data-ttu-id="f2940-113">Tenga en cuenta que `SendNotification` no se limita a enviar actualizaciones de contraseñas: la arquitectura de `SendNotification` también le permite enviar otros tipos de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="f2940-113">Note that `SendNotification` is not limited to sending password updates: the architecture of `SendNotification` also enables you to send other types of notifications.</span></span>  
  
3.  <span data-ttu-id="f2940-114">Solicitar actualizaciones de contraseñas de ENTSSO mediante `ISSOPSWrapper.ReceiveNotification`.</span><span class="sxs-lookup"><span data-stu-id="f2940-114">Request password updates from ENTSSO by using `ISSOPSWrapper.ReceiveNotification`.</span></span>  
  
     <span data-ttu-id="f2940-115">ENTSSO nunca llama a su adaptador ya que el adaptador de sincronización de contraseñas utiliza una tecnología de extracción.</span><span class="sxs-lookup"><span data-stu-id="f2940-115">Because the password sync adapter is a pull technology, ENTSSO never calls your adapter.</span></span> <span data-ttu-id="f2940-116">En su lugar, el adaptador llama periódicamente a `ReceiveNotification` para ver si están disponibles las actualizaciones de contraseña.</span><span class="sxs-lookup"><span data-stu-id="f2940-116">Instead, your adapter periodically calls `ReceiveNotification` to see whether any password updates are available.</span></span> <span data-ttu-id="f2940-117">La marca WAIT se puede configurar en `ReceiveNotification`.</span><span class="sxs-lookup"><span data-stu-id="f2940-117">You can choose to set the WAIT flag on `ReceiveNotification`.</span></span> <span data-ttu-id="f2940-118">Al configurar WAIT se bloquea el subproceso hasta que haya una notificación disponible.</span><span class="sxs-lookup"><span data-stu-id="f2940-118">Setting WAIT blocks the thread until a notification is available.</span></span>  
  
     <span data-ttu-id="f2940-119">Tenga en cuenta que ENTSSO proporciona a su adaptador un cambio de contraseña en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="f2940-119">Note that ENTSSO delivers a password change to your adapter in plain text.</span></span> <span data-ttu-id="f2940-120">Es responsabilidad del adaptador proteger la información referente a las contraseñas de una revelación incorrecta.</span><span class="sxs-lookup"><span data-stu-id="f2940-120">It is the responsibility of the adapter to protect that password information against incorrect disclosure.</span></span> <span data-ttu-id="f2940-121">También es responsabilidad del adaptador protegerse así mismo contra suplantaciones o ataques de otros orígenes no válidos, incluidas las suplantaciones del componente Aplicación auxiliar de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="f2940-121">It is also the responsibility of the adapter to protect itself against spoofing or attacks from other invalid sources, including spoofing of the Password Sync Helper component.</span></span>  
  
     <span data-ttu-id="f2940-122">Una vez que reciba una actualización de contraseñas de ENTSSO mediante el parámetro `pReceiveNotification`, debe pasar esta información a su sistema ajeno a Windows.</span><span class="sxs-lookup"><span data-stu-id="f2940-122">After you receive a password update from ENTSSO through the `pReceiveNotification` parameter, you must pass this information on to your non-Windows system.</span></span> <span data-ttu-id="f2940-123">Al igual que con `SendNotification`, debe determinar la mejor manera de comunicarse con el servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="f2940-123">As with `SendNotification`, you must determine the best way to communicate with the remote server.</span></span>  
  
4.  <span data-ttu-id="f2940-124">Desactivar el adaptador mediante `ISSOPSWrapper.ShutdownAdapter`.</span><span class="sxs-lookup"><span data-stu-id="f2940-124">Turn off your adapter using `ISSOPSWrapper.ShutdownAdapter`.</span></span>  
  
     <span data-ttu-id="f2940-125">`ShutdownApplication`debe ser el último método llamado por un adaptador e indica que el adaptador ya no enviará o recibirá actualizaciones de contraseñas a ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="f2940-125">`ShutdownApplication` should be the last method called by an adapter, and indicates that the adapter will no longer send or receive password updates to ENTSSO.</span></span>  
  
     <span data-ttu-id="f2940-126">Tenga en cuenta que ENTSSO almacena en búfer todos los cambios de contraseñas que realice un usuario mientras que el adaptador permanezca desactivado, teniendo en cuenta el límite del tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="f2940-126">Note that ENTSSO buffers any password changes a user makes while the adapter is shut down, up to a buffer size limit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2940-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2940-127">See Also</span></span>  
 <span data-ttu-id="f2940-128">[Programar con Enterprise Single Sign-On](../core/programming-with-enterprise-single-sign-on.md) </span><span class="sxs-lookup"><span data-stu-id="f2940-128">[Programming with Enterprise Single Sign-On](../core/programming-with-enterprise-single-sign-on.md) </span></span>  
 [<span data-ttu-id="f2940-129">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="f2940-129">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)