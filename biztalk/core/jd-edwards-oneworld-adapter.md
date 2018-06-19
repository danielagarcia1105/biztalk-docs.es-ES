---
title: Adaptador de JD Edwards OneWorld | Documentos de Microsoft
description: Instalar, recorre tutoriales paso a paso, obtenga información acerca de la arquitectura, utilizan la seguridad SSO, crear las aplicaciones, importar el archivo de enlace y agregar el control de excepciones cuando se usa el adaptador de BizTalk para J.D. Edwards OneWorld en BizTalk Server
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5df8cd89-d9df-41ca-9a2c-b9d7fbcd06f2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bde93503bff679faf2717edefb386aa2f43fc3e
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015933"
---
# <a name="jd-edwards-oneworld-adapter"></a><span data-ttu-id="0bd5c-104">Adaptador de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="0bd5c-104">JD Edwards OneWorld Adapter</span></span>
<span data-ttu-id="0bd5c-105">El adaptador de Microsoft BizTalk para JD Edwards OneWorld le permite usar las funciones empresariales de JD Edwards OneWorld en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0bd5c-105">Microsoft BizTalk Adapter for JD Edwards OneWorld enables you to use JD Edwards OneWorld business functions within BizTalk Server.</span></span> <span data-ttu-id="0bd5c-106">En las siguientes secciones se trata la configuración del adaptador de BizTalk para JD Edwards OneWorld para obtener acceso a información específica de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="0bd5c-106">The following sections discuss setting up BizTalk Adapter for JD Edwards OneWorld to access JD Edwards OneWorld-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="0bd5c-107">Introducción</span><span class="sxs-lookup"><span data-stu-id="0bd5c-107">Get started</span></span> 
<span data-ttu-id="0bd5c-108">[Introducción](../core/getting-started-with-biztalk-adapter-for-jd-edwards-oneworld.md) enumera los pasos necesarios para instalar el adaptador y, a través de un tutorial paso a paso.</span><span class="sxs-lookup"><span data-stu-id="0bd5c-108">[Get started](../core/getting-started-with-biztalk-adapter-for-jd-edwards-oneworld.md) lists the steps to install the adapter, and step through a tutorial.</span></span>

## <a name="architecture"></a><span data-ttu-id="0bd5c-109">Architecture</span><span class="sxs-lookup"><span data-stu-id="0bd5c-109">Architecture</span></span>
<span data-ttu-id="0bd5c-110">[Arquitectura](../core/planning-and-architecture17.md) detalla cómo funciona el adaptador, cómo instancias y las funciones se agrupan en tiempo de diseño y tiempo de ejecución, las limitaciones al consultar y recuperar listas y el uso de elementos de múltiples pedidos con este adaptador.</span><span class="sxs-lookup"><span data-stu-id="0bd5c-110">[Architecture](../core/planning-and-architecture17.md) details how the adapter works, how instances and functions are pooled at design time and run time, limitations when  querying and retrieving lists, and using multi-order items with this adapter.</span></span>

## <a name="security"></a><span data-ttu-id="0bd5c-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0bd5c-111">Security</span></span>
<span data-ttu-id="0bd5c-112">[Seguridad en el adaptador de BizTalk para JD Edwards OneWorld](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) implica el uso de Enterprise Single Sign-on (SSO) en BizTalk Server para proteger las aplicaciones que usan este adaptador.</span><span class="sxs-lookup"><span data-stu-id="0bd5c-112">[Security in BizTalk Adapter for JD Edwards OneWorld](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="0bd5c-113">Crear los artefactos</span><span class="sxs-lookup"><span data-stu-id="0bd5c-113">Create the artifacts</span></span>
<span data-ttu-id="0bd5c-114">[Crear los artefactos de la aplicación](../core/developing-applications3.md) muestra cómo agregar los artefactos de administración de BizTalk y en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0bd5c-114">[Create the application artifacts](../core/developing-applications3.md) shows you how to add the artifacts in BizTalk Administration, and in Visual Studio.</span></span> <span data-ttu-id="0bd5c-115">También muestra cómo utilizar propiedades de contexto de mensaje en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="0bd5c-115">It also shows how to use message context properties in an orchestration.</span></span>

## <a name="import-your-app"></a><span data-ttu-id="0bd5c-116">Importar la aplicación</span><span class="sxs-lookup"><span data-stu-id="0bd5c-116">Import your app</span></span>
<span data-ttu-id="0bd5c-117">[Implementación del adaptador de BizTalk para JD Edwards OneWorld](../core/deploying-biztalk-adapter-for-jd-edwards-oneworld.md) se describe cómo importar el archivo de enlace de la aplicación de administración de BizTalk y supera las limitaciones.</span><span class="sxs-lookup"><span data-stu-id="0bd5c-117">[Deploying BizTalk Adapter for JD Edwards OneWorld](../core/deploying-biztalk-adapter-for-jd-edwards-oneworld.md) discusses how to import your application binding file into BizTalk Administration, and goes over the limitations.</span></span> 

## <a name="exception-handling"></a><span data-ttu-id="0bd5c-118">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="0bd5c-118">Exception handling</span></span> 
<span data-ttu-id="0bd5c-119">[Control de excepciones de BizTalk Server](../core/using-biztalk-server-exception-handling1.md) proporciona directrices para actualizar el archivo jdearglist.txt y distintas formas de agregar a la orquestación para controlar las excepciones.</span><span class="sxs-lookup"><span data-stu-id="0bd5c-119">[BizTalk Server exception handling](../core/using-biztalk-server-exception-handling1.md) provides guidance on updating the jdearglist.txt file, and adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0bd5c-120">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="0bd5c-120">Troubleshooting</span></span>
<span data-ttu-id="0bd5c-121">[Solución de problemas](../core/troubleshooting-jd-edwards-oneworld.md) describen algunos errores comunes y las situaciones y se describe el seguimiento de eventos para Windows.</span><span class="sxs-lookup"><span data-stu-id="0bd5c-121">[Troubleshooting](../core/troubleshooting-jd-edwards-oneworld.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>

## <a name="data-types"></a><span data-ttu-id="0bd5c-122">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0bd5c-122">Data Types</span></span>
<span data-ttu-id="0bd5c-123">[Apéndice: Tipos de datos](../core/appendix-a-data-types.md) se enumeran los tipos de datos de ejemplo utilizados por este adaptador.</span><span class="sxs-lookup"><span data-stu-id="0bd5c-123">[Appendix: Data Types](../core/appendix-a-data-types.md) lists the sample data types used by this adapter.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0bd5c-124">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="0bd5c-124">UI reference</span></span>
<span data-ttu-id="0bd5c-125">[Referencia de interfaz de usuario para el adaptador de BizTalk para JDE OneWorld](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md) proporciona información detallada sobre los cuadros de diálogo y asistentes utilizados por este adaptador.</span><span class="sxs-lookup"><span data-stu-id="0bd5c-125">[UI Reference for BizTalk Adapter for JDE OneWorld](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md) provides details on the dialog boxes and wizards used by this adapter.</span></span> 