---
title: Adaptador TIBCO Enterprise Message Service | Documentos de Microsoft
description: "Instalar, recorre tutoriales paso a paso, obtenga información acerca de la arquitectura, utilizan la seguridad SSO, crear las aplicaciones, importar el archivo de enlace y agregar el control de excepciones cuando se usa el adaptador de BizTalk para TIBCO EMS en BizTalk Server"
ms.custom: 
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 362556d2-295c-4496-a429-ad7ecc44db76
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 988c7993dd407cb90e267e713a3195f897de9ceb
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-enterprise-message-service-adapter"></a><span data-ttu-id="ff153-103">Adaptador TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="ff153-103">TIBCO Enterprise Message Service Adapter</span></span>
<span data-ttu-id="ff153-104">Microsoft BizTalk Adapter para TIBCO Enterprise Message Service le permite publicar y suscribirse a las colas y temas administrados por TIBCO EMS mediante btsBizTalkServerNoVersion.</span><span class="sxs-lookup"><span data-stu-id="ff153-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service enables you to publish and subscribe to queues and topics managed by TIBCO EMS using btsBizTalkServerNoVersion.</span></span>  <span data-ttu-id="ff153-105">Las secciones siguientes tratan introducción, crear aplicaciones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="ff153-105">The following sections discuss getting started, creating applications, and more.</span></span>  
   
## <a name="get-started"></a><span data-ttu-id="ff153-106">Introducción</span><span class="sxs-lookup"><span data-stu-id="ff153-106">Get started</span></span>
<span data-ttu-id="ff153-107">[Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md) describe características del adaptador, instalar el adaptador e incluye algunos tutoriales.</span><span class="sxs-lookup"><span data-stu-id="ff153-107">[Get started](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md) describes adapter features, installing the adapter, and includes some tutorials.</span></span>

## <a name="architecture"></a><span data-ttu-id="ff153-108">Architecture</span><span class="sxs-lookup"><span data-stu-id="ff153-108">Architecture</span></span>
<span data-ttu-id="ff153-109">[Arquitectura](../core/planning-and-architecture16.md) describe cómo el adaptador funciona, proporciona algunos requisitos adicionales y enumera las limitaciones.</span><span class="sxs-lookup"><span data-stu-id="ff153-109">[Architecture](../core/planning-and-architecture16.md) describes how the adapter works, provides some additional requirements, and lists any limitations.</span></span>

## <a name="security"></a><span data-ttu-id="ff153-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ff153-110">Security</span></span>
<span data-ttu-id="ff153-111">[Seguridad](../core/security-in-biztalk-adapter-for-tibco-ems.md) implica el uso de Enterprise Single Sign-on (SSO) en BizTalk Server para proteger las aplicaciones que usan este adaptador.</span><span class="sxs-lookup"><span data-stu-id="ff153-111">[Security](../core/security-in-biztalk-adapter-for-tibco-ems.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="ff153-112">Crear los artefactos</span><span class="sxs-lookup"><span data-stu-id="ff153-112">Create the artifacts</span></span>
<span data-ttu-id="ff153-113">[Crear los artefactos de la aplicación](../core/developing-applications5.md) se enumeran los pasos para generar esquemas, cree el envío y recepción artefactos usados por este adaptador y cómo usar las propiedades de contexto de mensaje dentro de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="ff153-113">[Create the application artifacts](../core/developing-applications5.md) lists the steps to generate schemas, create the send and receive artifacts used by this adapter, and how to use the message context properties within an orchestration.</span></span>

## <a name="import-apps"></a><span data-ttu-id="ff153-114">Importar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ff153-114">Import apps</span></span>
<span data-ttu-id="ff153-115">[Importar enlaces](../core/deploying-biztalk-adapter-for-tibco-enterprise-message-service.md) se describe cómo importar el archivo de enlace de la aplicación de administración de BizTalk y supera las limitaciones.</span><span class="sxs-lookup"><span data-stu-id="ff153-115">[Import bindings](../core/deploying-biztalk-adapter-for-tibco-enterprise-message-service.md) discusses how to import your application binding file into BizTalk Administration, and goes over any limitations.</span></span> 

## <a name="handle-exceptions"></a><span data-ttu-id="ff153-116">Controlar excepciones</span><span class="sxs-lookup"><span data-stu-id="ff153-116">Handle exceptions</span></span>
<span data-ttu-id="ff153-117">[Usar el control de excepciones de BizTalk Server](../core/using-biztalk-server-exception-handling5.md) proporciona instrucciones sobre cómo agregar diferentes formas a la orquestación para controlar las excepciones.</span><span class="sxs-lookup"><span data-stu-id="ff153-117">[Use BizTalk Server Exception Handling](../core/using-biztalk-server-exception-handling5.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ff153-118">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="ff153-118">Troubleshooting</span></span>
 <span data-ttu-id="ff153-119">[Solución de problemas](../core/troubleshooting-tibco-enterprise-message-service.md) describen algunos errores comunes y las situaciones y se describe el seguimiento de eventos para Windows.</span><span class="sxs-lookup"><span data-stu-id="ff153-119">[Troubleshooting](../core/troubleshooting-tibco-enterprise-message-service.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>