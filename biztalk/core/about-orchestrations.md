---
title: Acerca de las orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations
- Orchestration Designer
- orchestrations, about orchestrations
- Orchestration Designer, about Orchestration Designer
ms.assetid: c0d9a3fb-da87-42cc-9e9e-e2c37232e606
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd3c1abeeb2c42c399a54aea4ba0128cc19bcd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-orchestrations"></a><span data-ttu-id="2004c-102">Acerca de las orquestaciones</span><span class="sxs-lookup"><span data-stu-id="2004c-102">About Orchestrations</span></span>
<span data-ttu-id="2004c-103">Una orquestación es una herramienta flexible y eficaz para la representación de un proceso empresarial ejecutable basado en el lenguaje XLANG/s.</span><span class="sxs-lookup"><span data-stu-id="2004c-103">An orchestration is a flexible, powerful tool for representing an executable business process based on XLANG/s language.</span></span> <span data-ttu-id="2004c-104">XLANG/s se puede ver como un lenguaje de mensajería con algunas de las capacidades de expresión de C#.</span><span class="sxs-lookup"><span data-stu-id="2004c-104">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span> <span data-ttu-id="2004c-105">Puede diseñar flujo, interpretar y generar datos, llamar código personalizado, así como organizar el proceso completo en un dibujo visual intuitivo y, en tiempo de ejecución, el motor de orquestaciones de BizTalk ejecuta los archivos XLANG/s que son los procesos empresariales ejecutables que produce el Diseñador de orquestaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2004c-105">You can design flow, interpret and generate data, call custom code, and organize the entire process in an intuitive visual drawing, and at run time, the BizTalk Orchestration Engine executes XLANG/s files which are the executable business processes that are produced by BizTalk Orchestration Designer.</span></span>  
  
 <span data-ttu-id="2004c-106">Los mensajes y las acciones de envío y recepción que se utilizan con ellos, así como los puertos a través de los que se transportan, son elementos fundamentales de una orquestación</span><span class="sxs-lookup"><span data-stu-id="2004c-106">Messages, the send and receive actions that operate on them, and the ports through which they are transported are all fundamental elements of an orchestration.</span></span> <span data-ttu-id="2004c-107">El mensaje es el medio a través del que las orquestaciones se comunican con el exterior y mediante el que se realizan las actividades de negocio electrónico.</span><span class="sxs-lookup"><span data-stu-id="2004c-107">The message is the medium by which orchestrations communicate with the outside world and by which e-business is conducted.</span></span>  
  
 <span data-ttu-id="2004c-108">**Recibir** y **enviar** formas encapsulan la funcionalidad que necesita para recibir mensajes en la orquestación y enviar mensajes desde ella.</span><span class="sxs-lookup"><span data-stu-id="2004c-108">**Receive** and **Send** shapes encapsulate the functionality you need to receive messages into your orchestration and send messages from it.</span></span> <span data-ttu-id="2004c-109">Debe familiarizarse con las distintas formas que el Diseñador de orquestaciones proporciona para representar el flujo lógico de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="2004c-109">You should become familiar with the various shapes that Orchestration Designer provides to represent the logical flow of your orchestration.</span></span>  
  
 <span data-ttu-id="2004c-110">Asimismo, debe comprender los conceptos avanzados relacionados con las orquestaciones, como servicios Web, correlación y transacciones de larga ejecución.</span><span class="sxs-lookup"><span data-stu-id="2004c-110">You should understand advanced orchestration concepts such as Web services, correlation, and long-running transactions.</span></span> <span data-ttu-id="2004c-111">Tal vez no necesite utilizar todas estas funciones, pero es útil saber lo que pueden hacer.</span><span class="sxs-lookup"><span data-stu-id="2004c-111">You might not need to use all of these facilities, but it is helpful to know what they can do for you.</span></span>  
  
 <span data-ttu-id="2004c-112">Los servicios Web son programas con interfaces que cumplen los estándares establecidos en el Lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="2004c-112">Web services are programs with interfaces that adhere to the standards set forth in the Web Services Description Language (WSDL).</span></span> <span data-ttu-id="2004c-113">Al definir de una forma estándar los tipos de mensajes, los puertos, los tipos de puertos y las operaciones, es posible establecer una comunicación eficaz entre sistemas diferentes.</span><span class="sxs-lookup"><span data-stu-id="2004c-113">By defining message types, ports, port types, and operations in a standard way, disparate systems can communicate effectively with each other.</span></span>  
  
 <span data-ttu-id="2004c-114">Una correlación es el mecanismo mediante el cual se asocian los mensajes con determinadas instancias en ejecución de una orquestación, de manera que el proceso empresarial obtiene la información adecuada cuando se ejecutan numerosas instancias y se envían y se reciben numerosos mensajes.</span><span class="sxs-lookup"><span data-stu-id="2004c-114">Correlation is the mechanism by which messages are associated with particular running instances of an orchestration, so that your business process gets the appropriate information when many instances are running and many messages are being sent back and forth.</span></span>  
  
 <span data-ttu-id="2004c-115">Las transacciones le permiten mantener de forma adecuada el estado de una orquestación si surgen problemas inesperados.</span><span class="sxs-lookup"><span data-stu-id="2004c-115">Transactions enable you to maintain the state of an orchestration appropriately if any unexpected issues arise.</span></span> <span data-ttu-id="2004c-116">El Diseñador de orquestaciones proporciona varios modos para controlar las excepciones, lo que le permite solucionar los errores de una manera controlada y predecible.</span><span class="sxs-lookup"><span data-stu-id="2004c-116">Orchestration Designer provides various ways to handle exceptions, which enable you to deal with errors in a controlled and predictable manner.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2004c-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2004c-117">In This Section</span></span>  
  
-   [<span data-ttu-id="2004c-118">La superficie de diseño de orquestación</span><span class="sxs-lookup"><span data-stu-id="2004c-118">The Orchestration Design Surface</span></span>](../core/the-orchestration-design-surface.md)  
  
-   [<span data-ttu-id="2004c-119">Ficha de orquestaciones de BizTalk, cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="2004c-119">BizTalk Orchestrations Tab, Toolbox</span></span>](../core/biztalk-orchestrations-tab-toolbox.md)  
  
-   [<span data-ttu-id="2004c-120">Pasos de desarrollo de una orquestación</span><span class="sxs-lookup"><span data-stu-id="2004c-120">Steps in Orchestration Development</span></span>](../core/steps-in-orchestration-development.md)  
  
-   [<span data-ttu-id="2004c-121">Consideraciones de seguridad para el desarrollo de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="2004c-121">Security Considerations for Developing Orchestrations</span></span>](../core/security-considerations-for-developing-orchestrations.md)  
  
-   [<span data-ttu-id="2004c-122">Lenguaje XLANG-s.</span><span class="sxs-lookup"><span data-stu-id="2004c-122">XLANG-s Language</span></span>](../core/xlang-s-language.md)  
  
-   [<span data-ttu-id="2004c-123">Acerca del motor de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="2004c-123">About the BizTalk Orchestration Engine</span></span>](../core/about-the-biztalk-orchestration-engine.md)