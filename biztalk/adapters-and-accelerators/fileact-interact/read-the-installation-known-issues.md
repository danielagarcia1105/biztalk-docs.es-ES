---
title: Lea la problemas conocidos de la instalación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245379f2-4048-4803-83ea-38dc23eb1a81
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4bc572cc18ca7d9d5515fe9f189287df5d1440f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022954"
---
# <a name="read-the-installation-known-issues"></a><span data-ttu-id="f61f0-102">Lea la problemas conocidos de la instalación</span><span class="sxs-lookup"><span data-stu-id="f61f0-102">Read the installation known issues</span></span>
[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]<span data-ttu-id="f61f0-103"> experimentan problemas conocidos enumerados en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="f61f0-103"> have known issues listed in the following sections.</span></span>  
  
## <a name="swift-does-not-support-stress-testing-on-integration-test-bed-itb-and-swiftnet-stub-environment"></a><span data-ttu-id="f61f0-104">SWIFT no admite pruebas de esfuerzo en el banco de pruebas de integración (ITB) y el entorno de código auxiliar de SWIFTNet</span><span class="sxs-lookup"><span data-stu-id="f61f0-104">SWIFT Does Not Support Stress Testing on Integration Test Bed (ITB) and SWIFTNet Stub Environment</span></span>  
 <span data-ttu-id="f61f0-105">El ITB no proporciona el acuerdo de nivel de servicio (SLA) en cuanto a rendimiento y no puede garantizar que los datos están completamente transmitidos o coherente.</span><span class="sxs-lookup"><span data-stu-id="f61f0-105">The ITB does not provide Service Level Agreement (SLA) in terms of throughput, and cannot guarantee that data is completely transmitted or consistent.</span></span> <span data-ttu-id="f61f0-106">Debe prueba de esfuerzo de la implementación en la producción de red en el entorno piloto.</span><span class="sxs-lookup"><span data-stu-id="f61f0-106">You should stress test your implementation on the production network in the Pilot environment.</span></span>  
  
 <span data-ttu-id="f61f0-107">Además, debe asegurarse de que todos los nodos (servidores, líneas y ancho de banda) están configuradas correctamente para evitar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="f61f0-107">Additionally, you must ensure that all of the nodes (server, lines, and bandwidth) are properly configured to avoid any data loss.</span></span> <span data-ttu-id="f61f0-108">A continuación se muestran los rendimientos de ejemplo típica:</span><span class="sxs-lookup"><span data-stu-id="f61f0-108">Following are typical sample throughputs:</span></span>  
  
- <span data-ttu-id="f61f0-109">Enviar interactuar/Fileact equipo acentuado: 20 mensajes/minuto</span><span class="sxs-lookup"><span data-stu-id="f61f0-109">Interact/Fileact Send under stressed computer: 20 messages/minute</span></span>  
  
- <span data-ttu-id="f61f0-110">De recepción de Fileact/interactuar en el equipo acentuado: 300-400 mensajes/minuto</span><span class="sxs-lookup"><span data-stu-id="f61f0-110">Interact/Fileact Receive under stressed computer: 300-400 messages/minute</span></span>  
  
  <span data-ttu-id="f61f0-111">Para obtener más información, consulte la documentación de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="f61f0-111">For more information, see your SWIFT documentation.</span></span>  
  
## <a name="messages-not-pushed-when-queue-is-open"></a><span data-ttu-id="f61f0-112">No se han analizado cuando se abre la cola de mensajes</span><span class="sxs-lookup"><span data-stu-id="f61f0-112">Messages Not Pushed When Queue Is Open</span></span>  
 <span data-ttu-id="f61f0-113">Cuando se usa la interacción o FileAct Store y el modo de avance (SnF), si la sesión con la cola está abierta y no se extraen los mensajes, a continuación, debe reiniciar SNLreceiver.exe.</span><span class="sxs-lookup"><span data-stu-id="f61f0-113">When you are using InterAct or FileAct Store and Forward (SnF) mode, if the session with the queue is open and messages are not being pushed, then you must restart SNLreceiver.exe.</span></span> <span data-ttu-id="f61f0-114">Esto evita un problema con SWIFT que se puede producir ocasionalmente.</span><span class="sxs-lookup"><span data-stu-id="f61f0-114">This avoids an issue with SWIFT that can occur occasionally.</span></span>  
  
## <a name="you-must-use-cdata-when-passing-characters-like--and--in-message"></a><span data-ttu-id="f61f0-115">Se debe usar CDATA al pasar caracteres como "<" y "&" en el mensaje</span><span class="sxs-lookup"><span data-stu-id="f61f0-115">You Must Use CDATA when Passing Characters like "<" and "&" in message</span></span>  
 <span data-ttu-id="f61f0-116">El término CDATA se utiliza sobre los datos de texto que no se deben analizar mediante el analizador XML.</span><span class="sxs-lookup"><span data-stu-id="f61f0-116">The term CDATA is used about text data that should not be parsed by the XML parser.</span></span>  <span data-ttu-id="f61f0-117">Caracteres como "<" y "&" no son válidas en los elementos XML.</span><span class="sxs-lookup"><span data-stu-id="f61f0-117">Characters like "<" and "&" are illegal in XML elements.</span></span> <span data-ttu-id="f61f0-118">"<", se generará un error porque el analizador lo interpreta como el inicio de un nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="f61f0-118">"<" will generate an error because the parser interprets it as the start of a new element.</span></span> <span data-ttu-id="f61f0-119">"&", se generará un error porque el analizador lo interpreta como el comienzo de una entidad de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f61f0-119">"&" will generate an error because the parser interprets it as the start of a character entity.</span></span> <span data-ttu-id="f61f0-120">El analizador omite todo el contenido dentro de una sección CDATA.</span><span class="sxs-lookup"><span data-stu-id="f61f0-120">Everything inside a CDATA section is ignored by the parser.</span></span> <span data-ttu-id="f61f0-121">Una sección CDATA comienza con "\<! [ CDATA ["y termina con"]]\>"</span><span class="sxs-lookup"><span data-stu-id="f61f0-121">A CDATA section starts with "\<![CDATA[" and ends with "]]\>"</span></span>  
  
## <a name="you-must-use-passthrough-pipelines-with-payload-only-mode"></a><span data-ttu-id="f61f0-122">Debe utilizar las canalizaciones Passthrough con modo de sólo carga</span><span class="sxs-lookup"><span data-stu-id="f61f0-122">You Must Use Passthrough Pipelines with Payload-Only Mode</span></span>  
 <span data-ttu-id="f61f0-123">Si usas el modo de sólo carga para el adaptador de InterAct, debe utilizar las canalizaciones de paso a través en ambos el envío y puertos de recepción si no usa las canalizaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f61f0-123">If you are using payload-only mode for the InterAct adapter, you must use pass-through pipelines on both the send and receive ports if you are not using custom pipelines.</span></span>  
  
## <a name="multiple-security-contexts-not-created-swiftnet-stub-computer"></a><span data-ttu-id="f61f0-124">Varios contextos de seguridad no creados (código auxiliar de SWIFTNet equipo)</span><span class="sxs-lookup"><span data-stu-id="f61f0-124">Multiple Security Contexts Not Created (SWIFTNet Stub Computer)</span></span>  
 <span data-ttu-id="f61f0-125">En un equipo de código auxiliar SWIFTNet, no se crean varios contextos de seguridad para los puertos de envío diferentes.</span><span class="sxs-lookup"><span data-stu-id="f61f0-125">On a SWIFTNet stub computer, multiple security contexts are not created for different send ports.</span></span> <span data-ttu-id="f61f0-126">Varios contextos de seguridad se crean en ITB.</span><span class="sxs-lookup"><span data-stu-id="f61f0-126">Multiple security contexts are created on ITB.</span></span>