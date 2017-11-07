---
title: "Adaptador de TIBCO Rendezvous de instalación, esquemas y limitaciones | Documentos de Microsoft"
description: "Instalación, la generación de esquema y las limitaciones del adaptador de BizTalk para TIBCO Rendezvous en BizTalk Server"
ms.custom: 
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6404e7e-f671-4c57-a222-0bbe7cbc334f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a158d4f627a553a87f0bc8fa08333a5864bb884
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="install-schemas-and-limitations-of-the-tibco-rendezvous-adapter"></a><span data-ttu-id="2159a-103">Instalar, esquemas y limitaciones del adaptador de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="2159a-103">Install, schemas, and limitations of the TIBCO Rendezvous adapter</span></span>

## <a name="install-and-setup"></a><span data-ttu-id="2159a-104">Instalación y configuración</span><span class="sxs-lookup"><span data-stu-id="2159a-104">Install and setup</span></span>

<span data-ttu-id="2159a-105">[Instalar y configurar los adaptadores para aplicaciones empresariales](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) incluye los pasos para instalar los adaptadores empresariales y también incluye información de la clave saber antes de instalar el adaptador y después de instalar el adaptador.</span><span class="sxs-lookup"><span data-stu-id="2159a-105">[Install and configure the adapters for enterprise applications](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) includes the steps to install the enterprise adapters, and also includes key information to know before you install the adapter, and after you install the adapter.</span></span> 

## <a name="generate-schemas"></a><span data-ttu-id="2159a-106">Generar esquemas</span><span class="sxs-lookup"><span data-stu-id="2159a-106">Generate schemas</span></span>
<span data-ttu-id="2159a-107">Un sistema TIBCO Rendezvous no incluye un repositorio de tipos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2159a-107">A TIBCO Rendezvous system does not include a message types repository.</span></span> <span data-ttu-id="2159a-108">Todos los análisis y construcciones de mensajes se incluyen en el tipo de aplicación Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="2159a-108">All the message construction and parsing is buried at the Rendezvous application level.</span></span> <span data-ttu-id="2159a-109">Debido a esta limitación, el adaptador no puede proporcionar capacidades de generación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="2159a-109">Because of this limitation, adapter cannot provide schema-generation capabilities.</span></span>  
  
<span data-ttu-id="2159a-110">Debe escribir un esquema y usar **Agregar elemento existente** en Visual Studio para importarlo para su uso en orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="2159a-110">You must write a schema, and use **Add Existing Item** in Visual Studio to import it for use in orchestrations.</span></span> <span data-ttu-id="2159a-111">Los esquemas son muy importantes para las herramientas de desarrollo de BizTalk Server y para la integración en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2159a-111">Schemas are very important for BizTalk Server development tools and for integration in Visual Studio.</span></span> <span data-ttu-id="2159a-112">Los programadores de BizTalk Server tienen la opción de proporcionar un esquema completo, minimalista o una versión intermedia.</span><span class="sxs-lookup"><span data-stu-id="2159a-112">BizTalk Server developers can choose to provide a complete schema, a minimalist schema, or a version somewhere in between.</span></span>  

## <a name="limitations"></a><span data-ttu-id="2159a-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="2159a-113">Limitations</span></span>

- <span data-ttu-id="2159a-114">No se garantiza la exclusividad del nombre de campo.</span><span class="sxs-lookup"><span data-stu-id="2159a-114">Field name uniqueness is not guaranteed.</span></span> <span data-ttu-id="2159a-115">Si un mensaje de TIBCO Rendezvous contiene dos nombres de campo que son iguales, el XML resultante no es válido.</span><span class="sxs-lookup"><span data-stu-id="2159a-115">If a TIBCO Rendezvous message contains two field names that are the same, the resulting XML is not valid.</span></span>  
  
-   <span data-ttu-id="2159a-116">No se proporciona la ordenación y clasificación de los campos.</span><span class="sxs-lookup"><span data-stu-id="2159a-116">Field ordering/sorting is not provided.</span></span>  
  
-   <span data-ttu-id="2159a-117">Según la documentación de TIBCO Rendezvous, los caracteres no imprimibles no se usan en nombres de asunto; sin embargo, sigue siendo posible usarlos.</span><span class="sxs-lookup"><span data-stu-id="2159a-117">According to TIBCO Rendezvous documentation, non-printable characters are not used in subject names; however, it is still possible that such characters are used.</span></span> <span data-ttu-id="2159a-118">BizTalk Adapter para TIBCO Rendezvous no admite nombres de asunto que contengan esos caracteres.</span><span class="sxs-lookup"><span data-stu-id="2159a-118">BizTalk Adapter for TIBCO Rendezvous does not support subject names containing those characters.</span></span>  
  
-   <span data-ttu-id="2159a-119">No se admite la conexión a daemons.</span><span class="sxs-lookup"><span data-stu-id="2159a-119">Secure connection to daemons is not supported.</span></span>  
  
-   <span data-ttu-id="2159a-120">No se admiten tipos de datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="2159a-120">Custom data types are not supported.</span></span>  
  
-   <span data-ttu-id="2159a-121">No se admite la mensajería certificada en el lado de transmisión.</span><span class="sxs-lookup"><span data-stu-id="2159a-121">Certified Messaging is not supported on the transmit side.</span></span>  
-   
## <a name="next-step"></a><span data-ttu-id="2159a-122">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="2159a-122">Next step</span></span>

[<span data-ttu-id="2159a-123">Tutoriales: Uso del Adaptador de Microsoft BizTalk para TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="2159a-123">Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous</span></span>](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md)  