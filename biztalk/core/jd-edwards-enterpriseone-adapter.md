---
title: Adaptador JD Edwards EnterpriseOne | Documentos de Microsoft
description: "Instalar, recorre tutoriales paso a paso, obtenga información acerca de la arquitectura, utilizan la seguridad SSO, crear las aplicaciones, importar el archivo de enlace y agregar el control de excepciones cuando se usa el adaptador de BizTalk para J.D. Edwards EnterpriseOne en BizTalk Server"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97f0f87a-59c3-4503-8da6-d6967dab820a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e1d82cafd20e8c86fbbf7daa42304ecb95c9aee
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="jd-edwards-enterpriseone-adapter"></a><span data-ttu-id="c6b99-104">Adaptador JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="c6b99-104">JD Edwards EnterpriseOne Adapter</span></span>
<span data-ttu-id="c6b99-105">Microsoft BizTalk Adapter para J.D.</span><span class="sxs-lookup"><span data-stu-id="c6b99-105">Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="c6b99-106">Edwards EnterpriseOne le permite usar las funciones de negocio de JD Edwards EnterpriseOne en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c6b99-106">Edwards EnterpriseOne enables you to use JD Edwards EnterpriseOne business functions within BizTalk Server.</span></span> <span data-ttu-id="c6b99-107">En las secciones siguientes se explica cómo configurar el adaptador para obtener acceso a la información de JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="c6b99-107">The following sections discuss setting up the adapter to access JD Edwards EnterpriseOne-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="c6b99-108">Introducción</span><span class="sxs-lookup"><span data-stu-id="c6b99-108">Get started</span></span>
<span data-ttu-id="c6b99-109">[Introducción](../core/getting-started-with-biztalk-adapter-for-jd-edwards-enterpriseone.md) enumera los pasos necesarios para instalar el adaptador y siga los pasos algunos tutoriales.</span><span class="sxs-lookup"><span data-stu-id="c6b99-109">[Get started](../core/getting-started-with-biztalk-adapter-for-jd-edwards-enterpriseone.md) lists the steps to install the adapter, and step through some tutorials.</span></span>

## <a name="architecture"></a><span data-ttu-id="c6b99-110">Architecture</span><span class="sxs-lookup"><span data-stu-id="c6b99-110">Architecture</span></span>
<span data-ttu-id="c6b99-111">[Arquitectura](../core/architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone.md) describe el tiempo de diseño y ejecutar elementos de tiempo del adaptador.</span><span class="sxs-lookup"><span data-stu-id="c6b99-111">[Architecture](../core/architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone.md) describes the design time and run time elements of the adapter.</span></span>

## <a name="security"></a><span data-ttu-id="c6b99-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c6b99-112">Security</span></span>
<span data-ttu-id="c6b99-113">[Seguridad](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md) implica el uso de Enterprise Single Sign-on (SSO) en BizTalk Server para proteger las aplicaciones que usan este adaptador.</span><span class="sxs-lookup"><span data-stu-id="c6b99-113">[Security](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="c6b99-114">Crear los artefactos</span><span class="sxs-lookup"><span data-stu-id="c6b99-114">Create the artifacts</span></span>
<span data-ttu-id="c6b99-115">[Crear los artefactos de la aplicación](../core/developing-applications2.md) muestra cómo agregar los artefactos de administración de BizTalk y en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c6b99-115">[Create the application artifacts](../core/developing-applications2.md) shows you how to add the artifacts in BizTalk Administration, and in Visual Studio.</span></span> <span data-ttu-id="c6b99-116">También muestra cómo utilizar propiedades de contexto de mensaje en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="c6b99-116">It also shows how to use message context properties in an orchestration.</span></span>

## <a name="import-your-app"></a><span data-ttu-id="c6b99-117">Importar la aplicación</span><span class="sxs-lookup"><span data-stu-id="c6b99-117">Import your app</span></span>
<span data-ttu-id="c6b99-118">[Implementar la aplicación](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md) se describe cómo importar el archivo de enlace de la aplicación de administración de BizTalk y supera las limitaciones.</span><span class="sxs-lookup"><span data-stu-id="c6b99-118">[Deploying your application](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md) discusses how to import your application binding file into BizTalk Administration, and goes over any limitations.</span></span> 

## <a name="exception-handling"></a><span data-ttu-id="c6b99-119">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="c6b99-119">Exception handling</span></span>
<span data-ttu-id="c6b99-120">[Control de excepciones de BizTalk Server](../core/using-biztalk-server-exception-handling3.md) proporciona instrucciones sobre cómo agregar diferentes formas a la orquestación para controlar las excepciones.</span><span class="sxs-lookup"><span data-stu-id="c6b99-120">[BizTalk Server Exception Handling](../core/using-biztalk-server-exception-handling3.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c6b99-121">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="c6b99-121">Troubleshooting</span></span>
<span data-ttu-id="c6b99-122">[Solucionar problemas del adaptador](../core/troubleshooting-jd-edwards-enterpriseone.md) describen algunos errores comunes y las situaciones y se describe el seguimiento de eventos para Windows.</span><span class="sxs-lookup"><span data-stu-id="c6b99-122">[Troubleshoot the adapter](../core/troubleshooting-jd-edwards-enterpriseone.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>

## <a name="reference"></a><span data-ttu-id="c6b99-123">Referencia</span><span class="sxs-lookup"><span data-stu-id="c6b99-123">Reference</span></span>
<span data-ttu-id="c6b99-124">[Referencia técnica de](../core/technical-reference6.md) incluye archivos de ejemplo y los tipos de datos de ejemplo utilizados por este adaptador.</span><span class="sxs-lookup"><span data-stu-id="c6b99-124">[Technical reference](../core/technical-reference6.md) includes sample files and sample data types used by this adapter.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c6b99-125">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c6b99-125">UI reference</span></span>
<span data-ttu-id="c6b99-126">[Referencia de interfaz de usuario](../core/ui-reference-for-biztalk-adapter-for-jd-edwards-enterpriseone.md) proporciona información detallada sobre los cuadros de diálogo y asistentes utilizados por este adaptador.</span><span class="sxs-lookup"><span data-stu-id="c6b99-126">[UI reference](../core/ui-reference-for-biztalk-adapter-for-jd-edwards-enterpriseone.md) provides details on the dialog boxes and wizards used by this adapter.</span></span> 