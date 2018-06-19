---
title: Lea la problemas conocidos de instalación | Documentos de Microsoft
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
ms.openlocfilehash: b6641e7974a0e1872b71794af6553d708e9619dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964690"
---
# <a name="read-the-installation-known-issues"></a><span data-ttu-id="8876e-102">Lea la problemas conocidos de instalación</span><span class="sxs-lookup"><span data-stu-id="8876e-102">Read the installation known issues</span></span>
[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]<span data-ttu-id="8876e-103">experimentan problemas conocidos enumerados en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="8876e-103"> have known issues listed in the following sections.</span></span>  
  
## <a name="swift-does-not-support-stress-testing-on-integration-test-bed-itb-and-swiftnet-stub-environment"></a><span data-ttu-id="8876e-104">SWIFT no admite pruebas de esfuerzo en el entorno de pruebas de integración (ITB) y el entorno de código auxiliar de SWIFTNet</span><span class="sxs-lookup"><span data-stu-id="8876e-104">SWIFT Does Not Support Stress Testing on Integration Test Bed (ITB) and SWIFTNet Stub Environment</span></span>  
 <span data-ttu-id="8876e-105">El ITB no proporciona el contrato de nivel de servicio (SLA) en cuanto a rendimiento y no puede garantizar que los datos son completamente transmitidos o coherente.</span><span class="sxs-lookup"><span data-stu-id="8876e-105">The ITB does not provide Service Level Agreement (SLA) in terms of throughput, and cannot guarantee that data is completely transmitted or consistent.</span></span> <span data-ttu-id="8876e-106">Debe prueba de carga de red de su implementación en producción en el entorno de prueba piloto.</span><span class="sxs-lookup"><span data-stu-id="8876e-106">You should stress test your implementation on the production network in the Pilot environment.</span></span>  
  
 <span data-ttu-id="8876e-107">Además, debe asegurarse de que todos los nodos (servidores, líneas y ancho de banda) están configurados correctamente para evitar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="8876e-107">Additionally, you must ensure that all of the nodes (server, lines, and bandwidth) are properly configured to avoid any data loss.</span></span> <span data-ttu-id="8876e-108">Siguientes son la capacidad de proceso de ejemplo típica:</span><span class="sxs-lookup"><span data-stu-id="8876e-108">Following are typical sample throughputs:</span></span>  
  
-   <span data-ttu-id="8876e-109">Enviar interactuar/Fileact equipo acentuado: 20 mensajes/minuto</span><span class="sxs-lookup"><span data-stu-id="8876e-109">Interact/Fileact Send under stressed computer: 20 messages/minute</span></span>  
  
-   <span data-ttu-id="8876e-110">Recepción interactuar/Fileact equipo acentuado: 300-400 mensajes por minuto</span><span class="sxs-lookup"><span data-stu-id="8876e-110">Interact/Fileact Receive under stressed computer: 300-400 messages/minute</span></span>  
  
 <span data-ttu-id="8876e-111">Para obtener más información, consulte la documentación de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="8876e-111">For more information, see your SWIFT documentation.</span></span>  
  
## <a name="messages-not-pushed-when-queue-is-open"></a><span data-ttu-id="8876e-112">No se inserta cuando se abre la cola de mensajes</span><span class="sxs-lookup"><span data-stu-id="8876e-112">Messages Not Pushed When Queue Is Open</span></span>  
 <span data-ttu-id="8876e-113">Cuando se usa InterAct o almacenamiento de FileAct y el modo de avance (SnF), si está abierta la sesión con la cola y no se extraen los mensajes, debe reiniciar SNLreceiver.exe.</span><span class="sxs-lookup"><span data-stu-id="8876e-113">When you are using InterAct or FileAct Store and Forward (SnF) mode, if the session with the queue is open and messages are not being pushed, then you must restart SNLreceiver.exe.</span></span> <span data-ttu-id="8876e-114">Esto evita que un problema con SWIFT que se puede producir ocasionalmente.</span><span class="sxs-lookup"><span data-stu-id="8876e-114">This avoids an issue with SWIFT that can occur occasionally.</span></span>  
  
## <a name="you-must-use-cdata-when-passing-characters-like--and--in-message"></a><span data-ttu-id="8876e-115">Se debe usar CDATA al pasar caracteres como "<" y "&" en el mensaje</span><span class="sxs-lookup"><span data-stu-id="8876e-115">You Must Use CDATA when Passing Characters like "<" and "&" in message</span></span>  
 <span data-ttu-id="8876e-116">El término CDATA se utiliza sobre los datos de texto que no se deben analizar el analizador XML.</span><span class="sxs-lookup"><span data-stu-id="8876e-116">The term CDATA is used about text data that should not be parsed by the XML parser.</span></span>  <span data-ttu-id="8876e-117">Caracteres como "<" y "&" no son válidos en los elementos XML.</span><span class="sxs-lookup"><span data-stu-id="8876e-117">Characters like "<" and "&" are illegal in XML elements.</span></span> <span data-ttu-id="8876e-118">"<", se generará un error porque el analizador lo interpreta como el inicio de un nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="8876e-118">"<" will generate an error because the parser interprets it as the start of a new element.</span></span> <span data-ttu-id="8876e-119">"&", se generará un error porque el analizador lo interpreta como el inicio de una entidad de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8876e-119">"&" will generate an error because the parser interprets it as the start of a character entity.</span></span> <span data-ttu-id="8876e-120">El analizador omite todo el contenido dentro de una sección CDATA.</span><span class="sxs-lookup"><span data-stu-id="8876e-120">Everything inside a CDATA section is ignored by the parser.</span></span> <span data-ttu-id="8876e-121">Una sección CDATA comienza con "\<! [ CDATA ["y termina con"]]\>"</span><span class="sxs-lookup"><span data-stu-id="8876e-121">A CDATA section starts with "\<![CDATA[" and ends with "]]\>"</span></span>  
  
## <a name="you-must-use-passthrough-pipelines-with-payload-only-mode"></a><span data-ttu-id="8876e-122">Debe utilizar las canalizaciones Passthrough con modo de solo carga</span><span class="sxs-lookup"><span data-stu-id="8876e-122">You Must Use Passthrough Pipelines with Payload-Only Mode</span></span>  
 <span data-ttu-id="8876e-123">Si se usa el modo de solo carga para el adaptador de InterAct, debe utilizar paso a través de canalizaciones de envío y puertos de recepción si no se utiliza canalizaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8876e-123">If you are using payload-only mode for the InterAct adapter, you must use pass-through pipelines on both the send and receive ports if you are not using custom pipelines.</span></span>  
  
## <a name="multiple-security-contexts-not-created-swiftnet-stub-computer"></a><span data-ttu-id="8876e-124">Varios contextos de seguridad no creados (código auxiliar de SWIFTNet equipo)</span><span class="sxs-lookup"><span data-stu-id="8876e-124">Multiple Security Contexts Not Created (SWIFTNet Stub Computer)</span></span>  
 <span data-ttu-id="8876e-125">En un equipo de código auxiliar SWIFTNet, no se crean varios contextos de seguridad para puertos de envío diferentes.</span><span class="sxs-lookup"><span data-stu-id="8876e-125">On a SWIFTNet stub computer, multiple security contexts are not created for different send ports.</span></span> <span data-ttu-id="8876e-126">Varios contextos de seguridad se crean en ITB.</span><span class="sxs-lookup"><span data-stu-id="8876e-126">Multiple security contexts are created on ITB.</span></span>