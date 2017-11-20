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
ms.openlocfilehash: 914d5cd9ac19e160c1f26df3f762f81fb89345d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="alert-subscription-management-commands"></a><span data-ttu-id="61269-102">Comandos de administración de suscripciones de alertas</span><span class="sxs-lookup"><span data-stu-id="61269-102">Alert Subscription Management Commands</span></span>
<span data-ttu-id="61269-103">Los comandos de administración de suscripciones de la utilidad de administración de BAM permiten trabajar con suscripciones de alertas.</span><span class="sxs-lookup"><span data-stu-id="61269-103">The BAM management utility subscription management commands allow you to work with alert subscriptions.</span></span>  
  
-   <span data-ttu-id="61269-104">get-subscription: Obtiene una lista de suscriptores a una alerta.</span><span class="sxs-lookup"><span data-stu-id="61269-104">get-subscription: Gets a list of subscribers to an alert.</span></span>  
  
-   <span data-ttu-id="61269-105">Agregar suscripción: agrega un suscriptor a una alerta.</span><span class="sxs-lookup"><span data-stu-id="61269-105">add-subscription: Adds a subscriber to an alert.</span></span>  
  
-   <span data-ttu-id="61269-106">Remove-subscription: quita un suscriptor de una alerta.</span><span class="sxs-lookup"><span data-stu-id="61269-106">remove-subscription: Removes a subscriber from an alert.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61269-107">Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="61269-107">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="61269-108">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="61269-108">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="61269-109">El conmutador puede utilizarse junto con cualquier comando normal de BM.</span><span class="sxs-lookup"><span data-stu-id="61269-109">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61269-110">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="61269-110">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-subscription-command"></a><span data-ttu-id="61269-111">get-subscription (comando)</span><span class="sxs-lookup"><span data-stu-id="61269-111">get-subscription Command</span></span>  
 <span data-ttu-id="61269-112">**Uso**</span><span class="sxs-lookup"><span data-stu-id="61269-112">**Usage**</span></span>  
  
 <span data-ttu-id="61269-113">**bm.exe get-subscriptions-View:\<nombre de vista >-alerta:\<nombre de la alerta > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="61269-113">**bm.exe get-subscriptions -View:\<view name> -Alert:\<alert name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="61269-114">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="61269-114">**Parameters**</span></span>  
  
|<span data-ttu-id="61269-115">Parámetro</span><span class="sxs-lookup"><span data-stu-id="61269-115">Parameter</span></span>|<span data-ttu-id="61269-116">Description</span><span class="sxs-lookup"><span data-stu-id="61269-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61269-117">Vista:\<nombre de vista ></span><span class="sxs-lookup"><span data-stu-id="61269-117">View:\<view name></span></span>|<span data-ttu-id="61269-118">Nombre de la vista en la que se va a especificar la alerta.</span><span class="sxs-lookup"><span data-stu-id="61269-118">The name of the view on which the alert is to be specified.</span></span>|  
|<span data-ttu-id="61269-119">Alerta:\<nombre de la alerta ></span><span class="sxs-lookup"><span data-stu-id="61269-119">Alert:\<alert name></span></span>|<span data-ttu-id="61269-120">Nombre de la alerta desde la que se va a obtener la suscripción.</span><span class="sxs-lookup"><span data-stu-id="61269-120">The name of the alert from which to get the subscription.</span></span>|  
|<span data-ttu-id="61269-121">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="61269-121">Server:\<server></span></span>|<span data-ttu-id="61269-122">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="61269-122">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="61269-123">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="61269-123">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="61269-124">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="61269-124">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="61269-125">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="61269-125">Database:\<database></span></span>|<span data-ttu-id="61269-126">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="61269-126">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="61269-127">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="61269-127">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="61269-128">Enumera todos los suscriptores de la alerta especificada.</span><span class="sxs-lookup"><span data-stu-id="61269-128">Lists all the subscribers to the specified alert.</span></span>  
  
 <span data-ttu-id="61269-129">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="61269-129">**Examples**</span></span>  
  
```  
bm.exe get-subscriptions -View:SalesManagerView -Alert:SalesTooLow  
bm.exe get-subscriptions -View:Shipments -Alert:SlowShipment -Server:Ship1  
```  
  
## <a name="add-subscription-command"></a><span data-ttu-id="61269-130">add-subscription (comando)</span><span class="sxs-lookup"><span data-stu-id="61269-130">add-subscription Command</span></span>  
 <span data-ttu-id="61269-131">**Uso**</span><span class="sxs-lookup"><span data-stu-id="61269-131">**Usage**</span></span>  
  
 <span data-ttu-id="61269-132">**suscripción de bm.exe-vista:\<nombre de la vista >-Alert:\<nombre de la alerta > - AccountName:\<nombre de cuenta >-tipo: [archivo de &#124; Email] [-correo electrónico:\<dirección de correo electrónico >] [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="61269-132">**bm.exe add-subscription -View:\<view name> -Alert:\<alert name> -AccountName:\<account name> -Type: [ File &#124; Email ][ -Email:\<e-mail address> ][ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="61269-133">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="61269-133">**Parameters**</span></span>  
  
|<span data-ttu-id="61269-134">Parámetro</span><span class="sxs-lookup"><span data-stu-id="61269-134">Parameter</span></span>|<span data-ttu-id="61269-135">Description</span><span class="sxs-lookup"><span data-stu-id="61269-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61269-136">Vista:\<nombre de vista ></span><span class="sxs-lookup"><span data-stu-id="61269-136">View:\<view name></span></span>|<span data-ttu-id="61269-137">Nombre de la vista en la que se especifica la alerta.</span><span class="sxs-lookup"><span data-stu-id="61269-137">The name of the view on which the alert is specified.</span></span>|  
|<span data-ttu-id="61269-138">Alerta:\<nombre de la alerta ></span><span class="sxs-lookup"><span data-stu-id="61269-138">Alert:\<alert name></span></span>|<span data-ttu-id="61269-139">Nombre de la alerta a la que se va a suscribir.</span><span class="sxs-lookup"><span data-stu-id="61269-139">The name of the alert to which to subscribe.</span></span>|  
|<span data-ttu-id="61269-140">AccountName:\<nombre de cuenta ></span><span class="sxs-lookup"><span data-stu-id="61269-140">AccountName:\<account name></span></span>|<span data-ttu-id="61269-141">Cuenta, con formato dominio\usuario, que se va a suscribir a la alerta.</span><span class="sxs-lookup"><span data-stu-id="61269-141">The account, in domain\user format, to subscribe to the alert.</span></span>|  
|<span data-ttu-id="61269-142">Tipo: [Archivo de &#124; Correo electrónico]</span><span class="sxs-lookup"><span data-stu-id="61269-142">Type: [ File &#124; Email ]</span></span>|<span data-ttu-id="61269-143">Tipo de entrega de la alerta.</span><span class="sxs-lookup"><span data-stu-id="61269-143">The delivery type of the alert.</span></span> <span data-ttu-id="61269-144">Si especifica un tipo de entrega de correo electrónico, debe incluir el parámetro de correo electrónico en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="61269-144">If you specify a delivery type of e-mail, you must include the e-mail parameter on the command line.</span></span>|  
|<span data-ttu-id="61269-145">Correo electrónico:\<dirección de correo electrónico ></span><span class="sxs-lookup"><span data-stu-id="61269-145">Email:\<e-mail address></span></span>|<span data-ttu-id="61269-146">Opcional: La dirección de correo electrónico a la que se va a entregar la notificación de alerta.</span><span class="sxs-lookup"><span data-stu-id="61269-146">Optional: The email address to which the alert notification will be delivered.</span></span>|  
|<span data-ttu-id="61269-147">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="61269-147">Server:\<server></span></span>|<span data-ttu-id="61269-148">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="61269-148">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="61269-149">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="61269-149">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="61269-150">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="61269-150">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="61269-151">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="61269-151">Database:\<database></span></span>|<span data-ttu-id="61269-152">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="61269-152">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="61269-153">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="61269-153">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="61269-154">Agrega una suscripción para la cuenta especificada a la alerta especificada.</span><span class="sxs-lookup"><span data-stu-id="61269-154">Adds a subscription for the specified account to the specified alert.</span></span>  
  
 <span data-ttu-id="61269-155">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="61269-155">**Examples**</span></span>  
  
```  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:File  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:Email -Email:useremail@domain.com  
```  
  
## <a name="remove-subscription-command"></a><span data-ttu-id="61269-156">remove-subscription (comando)</span><span class="sxs-lookup"><span data-stu-id="61269-156">remove-subscription Command</span></span>  
 <span data-ttu-id="61269-157">**Uso**</span><span class="sxs-lookup"><span data-stu-id="61269-157">**Usage**</span></span>  
  
 <span data-ttu-id="61269-158">**bm.exe remove-subscription-View:\<nombre de la vista >-alerta:\<nombre de la alerta > - AccountName:\<nombre de cuenta > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="61269-158">**bm.exe remove-subscription -View:\<view name> -Alert:\<alert name> -AccountName:\<account name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="61269-159">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="61269-159">**Parameters**</span></span>  
  
|<span data-ttu-id="61269-160">Parámetro</span><span class="sxs-lookup"><span data-stu-id="61269-160">Parameter</span></span>|<span data-ttu-id="61269-161">Description</span><span class="sxs-lookup"><span data-stu-id="61269-161">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61269-162">Vista:\<nombre de vista ></span><span class="sxs-lookup"><span data-stu-id="61269-162">View:\<view name></span></span>|<span data-ttu-id="61269-163">Nombre de la vista en la que se especifica la alerta.</span><span class="sxs-lookup"><span data-stu-id="61269-163">The name of the view on which the alert is specified.</span></span>|  
|<span data-ttu-id="61269-164">Alerta:\<nombre de la alerta ></span><span class="sxs-lookup"><span data-stu-id="61269-164">Alert:\<alert name></span></span>|<span data-ttu-id="61269-165">Nombre de la alerta.</span><span class="sxs-lookup"><span data-stu-id="61269-165">The name of the alert.</span></span>|  
|<span data-ttu-id="61269-166">AccountName:\<nombre de cuenta ></span><span class="sxs-lookup"><span data-stu-id="61269-166">AccountName:\<account name></span></span>|<span data-ttu-id="61269-167">Cuenta, con formato dominio\usuario, que se va a quitar de la alerta.</span><span class="sxs-lookup"><span data-stu-id="61269-167">The account, in domain\user format, to remove from the alert.</span></span>|  
|<span data-ttu-id="61269-168">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="61269-168">Server:\<server></span></span>|<span data-ttu-id="61269-169">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="61269-169">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="61269-170">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="61269-170">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="61269-171">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="61269-171">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="61269-172">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="61269-172">Database:\<database></span></span>|<span data-ttu-id="61269-173">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="61269-173">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="61269-174">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="61269-174">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="61269-175">Quita la suscripción de la cuenta especificada de la alerta especificada.</span><span class="sxs-lookup"><span data-stu-id="61269-175">Removes the subscription of the specified account from the specified alert.</span></span> <span data-ttu-id="61269-176">Se quitan todas las suscripciones para la cuenta especificada.</span><span class="sxs-lookup"><span data-stu-id="61269-176">All subscriptions for the specified account are removed.</span></span>  
  
 <span data-ttu-id="61269-177">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="61269-177">**Examples**</span></span>  
  
```  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:domain\user  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:user -Server:s1  
```  
  
## <a name="see-also"></a><span data-ttu-id="61269-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="61269-178">See Also</span></span>  
 [<span data-ttu-id="61269-179">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="61269-179">BAM Management Utility</span></span>](../core/bam-management-utility.md)