---
title: "Optimizar configuración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Max Concurrent Calls parameter
- optimizing, configuration
- configuring, optimizing
- messages, overload protection
ms.assetid: df0ae17b-fcfa-4e00-893c-63f4972d3822
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72b185d7738ac48d9a1dc3631c7c9faec9ac4b60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-configuration"></a><span data-ttu-id="f2bb1-102">Optimizar configuración</span><span class="sxs-lookup"><span data-stu-id="f2bb1-102">Optimizing Configuration</span></span>
<span data-ttu-id="f2bb1-103">Esta sección contiene información acerca de cómo optimizar la configuración del adaptador de BizTalk para PeopleSoft Enterprise e incluye una descripción de los parámetros necesarios para configurar el adaptador.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-103">This section contains information about how to optimize your configuration of BizTalk Adapter for PeopleSoft Enterprise and includes parameter descriptions for setting up the adapter.</span></span>  
  
## <a name="message-overload-protection"></a><span data-ttu-id="f2bb1-104">Protección ante sobrecarga de mensajes</span><span class="sxs-lookup"><span data-stu-id="f2bb1-104">Message Overload Protection</span></span>  
 <span data-ttu-id="f2bb1-105">El parámetro `Max Concurrent Calls` es una característica que permite optimizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-105">The `Max Concurrent Calls` parameter is a feature that enables you to optimize your configuration.</span></span> <span data-ttu-id="f2bb1-106">Este parámetro se usa en aquellas instancias en las que el rendimiento excede las capacidades de procesamiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-106">You use this parameter in instances where the throughput exceeds back-end processing capabilities.</span></span> <span data-ttu-id="f2bb1-107">Puede agregar el parámetro a los adaptadores en el **propiedades de transporte de puerto de envío** cuadro de diálogo para activar la protección de sobrecarga de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-107">You can add the parameter to the adapters in the **Send Port Transport Properties** dialog box to activate message overload protection.</span></span> <span data-ttu-id="f2bb1-108">El valor predeterminado es -1, lo que significa que las llamadas no están limitadas.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-108">The default is -1, meaning the calls are unlimited.</span></span>  
  
 <span data-ttu-id="f2bb1-109">Cuando el servidor BizTalk Server envía mensajes al adaptador de transmisión, recibe, en primer lugar, un lote del adaptador y, seguidamente, invoca `TransmitMessage()` en el lote para transmitir los distintos mensajes.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-109">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter and invokes `TransmitMessage()` on the batch to transmit each message.</span></span> <span data-ttu-id="f2bb1-110">A continuación, el servidor BizTalk Server invoca `Done()` en el lote, y el adaptador comienza a transmitir los mensajes al servidor.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-110">When done, BizTalk Server invokes `Done()` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="f2bb1-111">Si el servidor obtiene varios lotes antes de que se invoque `Done`, puede que el comando `Done` nunca se produzca.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-111">If BizTalk Server obtains multiple batches before `Done` is invoked, the `Done` command might never occur.</span></span> <span data-ttu-id="f2bb1-112">El establecimiento del número máximo de mensajes que se van a incluir en un lote le permite controlar los mensajes que se van a transmitir al servidor.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-112">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span> <span data-ttu-id="f2bb1-113">Este parámetro se aplica transcurrido un minuto.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-113">Changing this parameter takes effect in a minute.</span></span> <span data-ttu-id="f2bb1-114">BizTalk Server debe recuperar los cambios de la configuración del adaptador que se haya guardado en la base de datos de SQL.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-114">BizTalk Server must retrieve the changes to the adapter configuration that is saved in the SQL database.</span></span>  
  
#### <a name="to-change-the-max-concurrent-calls-parameter"></a><span data-ttu-id="f2bb1-115">Procedimiento para cambiar el parámetro Número máximo de llamadas concurrentes</span><span class="sxs-lookup"><span data-stu-id="f2bb1-115">To change the Max Concurrent Calls parameter</span></span>  
  
1.  <span data-ttu-id="f2bb1-116">En el **propiedades de transporte de puerto de envío** diálogo cuadro, escriba un **conexión** valor.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-116">In the **Send Port Transport Properties** dialog box, enter a **Connection** value.</span></span>  
  
     <span data-ttu-id="f2bb1-117">El valor predeterminado es 40 sesiones.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-117">The default value is 40 sessions.</span></span> <span data-ttu-id="f2bb1-118">Si usa un valor más pequeño, podría experimentar una degradación del rendimiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-118">If you use a smaller value, you might experience degradation in run-time performance.</span></span> <span data-ttu-id="f2bb1-119">También puede ocurrir lo contrario, un valor mayor puede sobrepasar la capacidad del servidor y resultar en errores de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-119">The opposite is also true; a bigger value could exceed the ability of the server and result in run-time errors.</span></span>  
  
2.  <span data-ttu-id="f2bb1-120">Seleccione **Sí** para **agente de actualización** para forzar que los procesos runtimeagent.exe y browsingagent.exe se reinicie automáticamente cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-120">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="f2bb1-121">Por ejemplo, si desea que el proceso se reinicie automáticamente si éste pierde la conexión con el servidor, o si agrega algo al servidor y no se muestra en el asistente para adaptadores de Microsoft para su selección.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-121">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
     <span data-ttu-id="f2bb1-122">El **agente de actualización** parámetro actualiza la exploración y los agentes de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-122">The **Refresh Agent** parameter refreshes both the browsing and the run-time agents.</span></span> <span data-ttu-id="f2bb1-123">El archivo runtimeagent.exe se actualiza tras una demora de un minuto o en la siguiente llamada de envío.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-123">The runtimeagent.exe updates after a delay of one minute or at the next send call.</span></span>  
  
3.  <span data-ttu-id="f2bb1-124">Proporcione credenciales para tener acceso al sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-124">Provide credentials to access the PeopleSoft system.</span></span>  
  
     <span data-ttu-id="f2bb1-125">Puede usar dos métodos para tener acceso al sistema:</span><span class="sxs-lookup"><span data-stu-id="f2bb1-125">You can use two methods to access the system:</span></span>  
  
    -   <span data-ttu-id="f2bb1-126">Credenciales de inicio de sesión (parámetros de inicio de sesión de propiedades de transporte)</span><span class="sxs-lookup"><span data-stu-id="f2bb1-126">Login Credentials (Transport Properties Login parameters)</span></span>  
  
    -   <span data-ttu-id="f2bb1-127">Inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="f2bb1-127">Single Sign-On</span></span>  
  
4.  <span data-ttu-id="f2bb1-128">Seleccione **Sí** para **usar SSO** usar Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-128">Select **Yes** for **Use SSO** to use Single Sign-On.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f2bb1-129">Para obtener más información, consulte [utilizando Single Sign-On](../core/using-single-sign-on2.md).</span><span class="sxs-lookup"><span data-stu-id="f2bb1-129">For more information, see [Using Single Sign-On](../core/using-single-sign-on2.md).</span></span>  
  
5.  <span data-ttu-id="f2bb1-130">Seleccione una aplicación afiliada en la lista.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-130">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="f2bb1-131">Una aplicación afiliada, creada por herramientas de inicio de sesión único de la empresa, representa una aplicación como PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-131">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as PeopleSoft.</span></span> <span data-ttu-id="f2bb1-132">El adaptador de Microsoft BizTalk para PeopleSoft Enterprise usa las credenciales del usuario de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-132">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses the credentials of an application user.</span></span> <span data-ttu-id="f2bb1-133">Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-133">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="f2bb1-134">Las credenciales son aquellas que pertenecen al usuario (al usuario de la aplicación) que inició el proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-134">The credentials are those of the user (the application user) who launched the BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f2bb1-135">Para obtener más información sobre cómo crear aplicaciones afiliadas, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications2.md), o la Ayuda en pantalla de Microsoft BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-135">For more information about how to create affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md), or the Microsoft BizTalk Server online Help.</span></span>  
  
6.  <span data-ttu-id="f2bb1-136">Después de proporcionar toda la información necesaria para aceptar la información de conexión, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-136">After providing all required information to accept the connection information, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f2bb1-137">Se deben establecer los parámetros de conexión para el adaptador de BizTalk para PeopleSoft Enterprise para tener acceso a PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-137">You must set connection parameters for the BizTalk Adapter for PeopleSoft Enterprise to access PeopleSoft.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2bb1-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2bb1-138">See Also</span></span>  
 [<span data-ttu-id="f2bb1-139">Crear controladores de envío de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="f2bb1-139">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)