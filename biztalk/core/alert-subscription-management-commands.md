---
title: "Comandos de administración de suscripciones de alerta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cd6ad27-6217-466a-b616-4b26fb31b0af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02234637e38bb59e71c0f435ee24feef39e09e91
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="alert-subscription-management-commands"></a><span data-ttu-id="6eef8-102">Comandos de administración de suscripciones de alertas</span><span class="sxs-lookup"><span data-stu-id="6eef8-102">Alert Subscription Management Commands</span></span>
<span data-ttu-id="6eef8-103">Los comandos de administración de suscripciones de la utilidad de administración de BAM permiten trabajar con suscripciones de alertas.</span><span class="sxs-lookup"><span data-stu-id="6eef8-103">The BAM management utility subscription management commands allow you to work with alert subscriptions.</span></span>  
  
-   <span data-ttu-id="6eef8-104">get-subscription: Obtiene una lista de suscriptores a una alerta.</span><span class="sxs-lookup"><span data-stu-id="6eef8-104">get-subscription: Gets a list of subscribers to an alert.</span></span>  
  
-   <span data-ttu-id="6eef8-105">Agregar suscripción: agrega un suscriptor a una alerta.</span><span class="sxs-lookup"><span data-stu-id="6eef8-105">add-subscription: Adds a subscriber to an alert.</span></span>  
  
-   <span data-ttu-id="6eef8-106">Remove-subscription: quita un suscriptor de una alerta.</span><span class="sxs-lookup"><span data-stu-id="6eef8-106">remove-subscription: Removes a subscriber from an alert.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6eef8-107">Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="6eef8-107">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="6eef8-108">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6eef8-108">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="6eef8-109">El conmutador puede utilizarse junto con cualquier comando normal de BM.</span><span class="sxs-lookup"><span data-stu-id="6eef8-109">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6eef8-110">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="6eef8-110">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-subscription-command"></a><span data-ttu-id="6eef8-111">get-subscription (comando)</span><span class="sxs-lookup"><span data-stu-id="6eef8-111">get-subscription Command</span></span>  
 <span data-ttu-id="6eef8-112">**Uso**</span><span class="sxs-lookup"><span data-stu-id="6eef8-112">**Usage**</span></span>  
  
 <span data-ttu-id="6eef8-113">**bm.exe get-subscriptions-View:\<nombre de la vista\> -alerta:\<nombre de la alerta\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="6eef8-113">**bm.exe get-subscriptions -View:\<view name\> -Alert:\<alert name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="6eef8-114">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="6eef8-114">**Parameters**</span></span>  
  
|<span data-ttu-id="6eef8-115">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6eef8-115">Parameter</span></span>|<span data-ttu-id="6eef8-116">Description</span><span class="sxs-lookup"><span data-stu-id="6eef8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6eef8-117">Vista:\<nombre de vista\></span><span class="sxs-lookup"><span data-stu-id="6eef8-117">View:\<view name\></span></span>|<span data-ttu-id="6eef8-118">Nombre de la vista en la que se va a especificar la alerta.</span><span class="sxs-lookup"><span data-stu-id="6eef8-118">The name of the view on which the alert is to be specified.</span></span>|  
|<span data-ttu-id="6eef8-119">Alerta:\<nombre de la alerta\></span><span class="sxs-lookup"><span data-stu-id="6eef8-119">Alert:\<alert name\></span></span>|<span data-ttu-id="6eef8-120">Nombre de la alerta desde la que se va a obtener la suscripción.</span><span class="sxs-lookup"><span data-stu-id="6eef8-120">The name of the alert from which to get the subscription.</span></span>|  
|<span data-ttu-id="6eef8-121">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="6eef8-121">Server:\<server\></span></span>|<span data-ttu-id="6eef8-122">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="6eef8-122">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="6eef8-123">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="6eef8-123">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="6eef8-124">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="6eef8-124">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="6eef8-125">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="6eef8-125">Database:\<database\></span></span>|<span data-ttu-id="6eef8-126">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="6eef8-126">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="6eef8-127">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="6eef8-127">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="6eef8-128">Enumera todos los suscriptores de la alerta especificada.</span><span class="sxs-lookup"><span data-stu-id="6eef8-128">Lists all the subscribers to the specified alert.</span></span>  
  
 <span data-ttu-id="6eef8-129">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="6eef8-129">**Examples**</span></span>  
  
```  
bm.exe get-subscriptions -View:SalesManagerView -Alert:SalesTooLow  
bm.exe get-subscriptions -View:Shipments -Alert:SlowShipment -Server:Ship1  
```  
  
## <a name="add-subscription-command"></a><span data-ttu-id="6eef8-130">add-subscription (comando)</span><span class="sxs-lookup"><span data-stu-id="6eef8-130">add-subscription Command</span></span>  
 <span data-ttu-id="6eef8-131">**Uso**</span><span class="sxs-lookup"><span data-stu-id="6eef8-131">**Usage**</span></span>  
  
 <span data-ttu-id="6eef8-132">**suscripción de bm.exe-View:\<nombre de la vista\> -alerta:\<nombre de la alerta\> - AccountName:\<nombre de la cuenta\> -tipo: [archivo de &#124; Email] [-correo electrónico:\<dirección de correo electrónico\> ] [-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="6eef8-132">**bm.exe add-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\> -Type: [ File &#124; Email ][ -Email:\<e-mail address\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="6eef8-133">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="6eef8-133">**Parameters**</span></span>  
  
|<span data-ttu-id="6eef8-134">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6eef8-134">Parameter</span></span>|<span data-ttu-id="6eef8-135">Description</span><span class="sxs-lookup"><span data-stu-id="6eef8-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6eef8-136">Vista:\<nombre de vista\></span><span class="sxs-lookup"><span data-stu-id="6eef8-136">View:\<view name\></span></span>|<span data-ttu-id="6eef8-137">Nombre de la vista en la que se especifica la alerta.</span><span class="sxs-lookup"><span data-stu-id="6eef8-137">The name of the view on which the alert is specified.</span></span>|  
|<span data-ttu-id="6eef8-138">Alerta:\<nombre de la alerta\></span><span class="sxs-lookup"><span data-stu-id="6eef8-138">Alert:\<alert name\></span></span>|<span data-ttu-id="6eef8-139">Nombre de la alerta a la que se va a suscribir.</span><span class="sxs-lookup"><span data-stu-id="6eef8-139">The name of the alert to which to subscribe.</span></span>|  
|<span data-ttu-id="6eef8-140">AccountName:\<nombre de cuenta\></span><span class="sxs-lookup"><span data-stu-id="6eef8-140">AccountName:\<account name\></span></span>|<span data-ttu-id="6eef8-141">Cuenta, con formato dominio\usuario, que se va a suscribir a la alerta.</span><span class="sxs-lookup"><span data-stu-id="6eef8-141">The account, in domain\user format, to subscribe to the alert.</span></span>|  
|<span data-ttu-id="6eef8-142">Tipo: [Archivo de &#124; Correo electrónico]</span><span class="sxs-lookup"><span data-stu-id="6eef8-142">Type: [ File &#124; Email ]</span></span>|<span data-ttu-id="6eef8-143">Tipo de entrega de la alerta.</span><span class="sxs-lookup"><span data-stu-id="6eef8-143">The delivery type of the alert.</span></span> <span data-ttu-id="6eef8-144">Si especifica un tipo de entrega de correo electrónico, debe incluir el parámetro de correo electrónico en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6eef8-144">If you specify a delivery type of e-mail, you must include the e-mail parameter on the command line.</span></span>|  
|<span data-ttu-id="6eef8-145">Correo electrónico:\<dirección de correo electrónico\></span><span class="sxs-lookup"><span data-stu-id="6eef8-145">Email:\<e-mail address\></span></span>|<span data-ttu-id="6eef8-146">Opcional: La dirección de correo electrónico a la que se va a entregar la notificación de alerta.</span><span class="sxs-lookup"><span data-stu-id="6eef8-146">Optional: The email address to which the alert notification will be delivered.</span></span>|  
|<span data-ttu-id="6eef8-147">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="6eef8-147">Server:\<server\></span></span>|<span data-ttu-id="6eef8-148">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="6eef8-148">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="6eef8-149">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="6eef8-149">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="6eef8-150">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="6eef8-150">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="6eef8-151">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="6eef8-151">Database:\<database\></span></span>|<span data-ttu-id="6eef8-152">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="6eef8-152">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="6eef8-153">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="6eef8-153">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="6eef8-154">Agrega una suscripción para la cuenta especificada a la alerta especificada.</span><span class="sxs-lookup"><span data-stu-id="6eef8-154">Adds a subscription for the specified account to the specified alert.</span></span>  
  
 <span data-ttu-id="6eef8-155">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="6eef8-155">**Examples**</span></span>  
  
```  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:File  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:Email -Email:useremail@domain.com  
```  
  
## <a name="remove-subscription-command"></a><span data-ttu-id="6eef8-156">remove-subscription (comando)</span><span class="sxs-lookup"><span data-stu-id="6eef8-156">remove-subscription Command</span></span>  
 <span data-ttu-id="6eef8-157">**Uso**</span><span class="sxs-lookup"><span data-stu-id="6eef8-157">**Usage**</span></span>  
  
 <span data-ttu-id="6eef8-158">**bm.exe remove-subscription-View:\<nombre de la vista\> -alerta:\<nombre de la alerta\> - AccountName:\<nombre de la cuenta\>[-Server:\<server\> ] [- Base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="6eef8-158">**bm.exe remove-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="6eef8-159">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="6eef8-159">**Parameters**</span></span>  
  
|<span data-ttu-id="6eef8-160">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6eef8-160">Parameter</span></span>|<span data-ttu-id="6eef8-161">Description</span><span class="sxs-lookup"><span data-stu-id="6eef8-161">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6eef8-162">Vista:\<nombre de vista\></span><span class="sxs-lookup"><span data-stu-id="6eef8-162">View:\<view name\></span></span>|<span data-ttu-id="6eef8-163">Nombre de la vista en la que se especifica la alerta.</span><span class="sxs-lookup"><span data-stu-id="6eef8-163">The name of the view on which the alert is specified.</span></span>|  
|<span data-ttu-id="6eef8-164">Alerta:\<nombre de la alerta\></span><span class="sxs-lookup"><span data-stu-id="6eef8-164">Alert:\<alert name\></span></span>|<span data-ttu-id="6eef8-165">Nombre de la alerta.</span><span class="sxs-lookup"><span data-stu-id="6eef8-165">The name of the alert.</span></span>|  
|<span data-ttu-id="6eef8-166">AccountName:\<nombre de cuenta\></span><span class="sxs-lookup"><span data-stu-id="6eef8-166">AccountName:\<account name\></span></span>|<span data-ttu-id="6eef8-167">Cuenta, con formato dominio\usuario, que se va a quitar de la alerta.</span><span class="sxs-lookup"><span data-stu-id="6eef8-167">The account, in domain\user format, to remove from the alert.</span></span>|  
|<span data-ttu-id="6eef8-168">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="6eef8-168">Server:\<server\></span></span>|<span data-ttu-id="6eef8-169">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="6eef8-169">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="6eef8-170">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="6eef8-170">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="6eef8-171">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="6eef8-171">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="6eef8-172">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="6eef8-172">Database:\<database\></span></span>|<span data-ttu-id="6eef8-173">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="6eef8-173">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="6eef8-174">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="6eef8-174">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="6eef8-175">Quita la suscripción de la cuenta especificada de la alerta especificada.</span><span class="sxs-lookup"><span data-stu-id="6eef8-175">Removes the subscription of the specified account from the specified alert.</span></span> <span data-ttu-id="6eef8-176">Se quitan todas las suscripciones para la cuenta especificada.</span><span class="sxs-lookup"><span data-stu-id="6eef8-176">All subscriptions for the specified account are removed.</span></span>  
  
 <span data-ttu-id="6eef8-177">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="6eef8-177">**Examples**</span></span>  
  
```  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:domain\user  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:user -Server:s1  
```  
  
## <a name="see-also"></a><span data-ttu-id="6eef8-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="6eef8-178">See Also</span></span>  
 [<span data-ttu-id="6eef8-179">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="6eef8-179">BAM Management Utility</span></span>](../core/bam-management-utility.md)