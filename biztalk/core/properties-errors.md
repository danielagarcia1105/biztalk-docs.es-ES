---
title: Errores de propiedades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d297db1a-352c-4e5a-b0aa-6edae8d74824
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4c03358ba08df939e7058a6d73603969dcddd8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265084"
---
# <a name="properties-errors"></a><span data-ttu-id="3c6ca-102">Errores de propiedades</span><span class="sxs-lookup"><span data-stu-id="3c6ca-102">Properties Errors</span></span>
<span data-ttu-id="3c6ca-103">En esta sección se incluye información detallada para diagnosticar y resolver errores de propiedades de WCF.</span><span class="sxs-lookup"><span data-stu-id="3c6ca-103">This section contains detailed information for diagnosing and resolving WCF Properties errors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c6ca-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3c6ca-104">In This Section</span></span>  
  
-   [<span data-ttu-id="3c6ca-105">Error al cargar propiedades</span><span class="sxs-lookup"><span data-stu-id="3c6ca-105">Error loading properties</span></span>](../core/error-loading-properties.md)  
  
-   [<span data-ttu-id="3c6ca-106">Error al guardar propiedades</span><span class="sxs-lookup"><span data-stu-id="3c6ca-106">Error saving properties</span></span>](../core/error-saving-properties.md)  
  
-   [<span data-ttu-id="3c6ca-107">Ubicación del proyecto no válida</span><span class="sxs-lookup"><span data-stu-id="3c6ca-107">Invalid project location</span></span>](../core/invalid-project-location.md)  
  
-   [<span data-ttu-id="3c6ca-108">Elemento que falta parte de mensaje</span><span class="sxs-lookup"><span data-stu-id="3c6ca-108">Message part missing element</span></span>](../core/message-part-missing-element.md)  
  
-   [<span data-ttu-id="3c6ca-109">No se admiten los tipos de mensajes sin partes</span><span class="sxs-lookup"><span data-stu-id="3c6ca-109">Message types without parts are not supported</span></span>](../core/message-types-without-parts-are-not-supported.md)  
  
-   [<span data-ttu-id="3c6ca-110">OutboundCustomHeaders no tiene el formato correcto</span><span class="sxs-lookup"><span data-stu-id="3c6ca-110">OutboundCustomHeaders does not have correct format</span></span>](../core/outboundcustomheaders-does-not-have-correct-format.md)  
  
-   [<span data-ttu-id="3c6ca-111">La ubicación del proyecto no está vacía</span><span class="sxs-lookup"><span data-stu-id="3c6ca-111">The project location is not empty</span></span>](../core/the-project-location-is-not-empty.md)  
  
-   [<span data-ttu-id="3c6ca-112">No se puede crear el elemento de configuración de comportamiento de punto de conexión de configuración XML</span><span class="sxs-lookup"><span data-stu-id="3c6ca-112">Unable to create endpoint behavior configuration element from XML configuration</span></span>](../core/unable-to-create-endpoint-behavior-configuration-element-from-xml-configuration.md)  
  
-   [<span data-ttu-id="3c6ca-113">No se puede crear el elemento de configuración de comportamiento de servicio de configuración XML</span><span class="sxs-lookup"><span data-stu-id="3c6ca-113">Unable to create service behavior configuration element from XML configuration</span></span>](../core/unable-to-create-service-behavior-configuration-element-from-xml-configuration.md)  
  
-   [<span data-ttu-id="3c6ca-114">No se puede exportar la configuración de punto de conexión de cliente</span><span class="sxs-lookup"><span data-stu-id="3c6ca-114">Unable to export client endpoint configuration</span></span>](../core/unable-to-export-client-endpoint-configuration.md)  
  
-   [<span data-ttu-id="3c6ca-115">No se puede exportar la configuración de punto de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="3c6ca-115">Unable to export service endpoint configuration</span></span>](../core/unable-to-export-service-endpoint-configuration.md)  
  
-   [<span data-ttu-id="3c6ca-116">No se puede encontrar el contenido de la expresión de ruta de acceso del cuerpo de entrada</span><span class="sxs-lookup"><span data-stu-id="3c6ca-116">Unable to find content for inbound body path expression</span></span>](../core/unable-to-find-content-for-inbound-body-path-expression.md)  
  
-   [<span data-ttu-id="3c6ca-117">No se ha podido encontrar a una coincidencia para la expresión de ruta de acceso del cuerpo de entrada</span><span class="sxs-lookup"><span data-stu-id="3c6ca-117">Unable to find match for inbound body path expression</span></span>](../core/unable-to-find-match-for-inbound-body-path-expression.md)  
  
-   [<span data-ttu-id="3c6ca-118">Elemento raíz inesperado.</span><span class="sxs-lookup"><span data-stu-id="3c6ca-118">Unexpected root element</span></span>](../core/unexpected-root-element.md)  
  
-   [<span data-ttu-id="3c6ca-119">Cálculo de referencias de tipo de mensaje saliente no reconocido</span><span class="sxs-lookup"><span data-stu-id="3c6ca-119">Unrecognized outbound message marshalling type</span></span>](../core/unrecognized-outbound-message-marshalling-type.md)  
  
-   [<span data-ttu-id="3c6ca-120">Conjunto de algoritmos de seguridad no compatible</span><span class="sxs-lookup"><span data-stu-id="3c6ca-120">Unsupported security algorithm suite</span></span>](../core/unsupported-security-algorithm-suite.md)  
  
-   [<span data-ttu-id="3c6ca-121">Protocolo de transacción no compatible</span><span class="sxs-lookup"><span data-stu-id="3c6ca-121">Unsupported transaction protocol</span></span>](../core/unsupported-transaction-protocol.md)  
  
-   [<span data-ttu-id="3c6ca-122">Cliente de WCF debe permitir la suplantación usar el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="3c6ca-122">WCF client must allow impersonation to use Single Sign-On</span></span>](../core/wcf-client-must-allow-impersonation-to-use-single-sign-on.md)  
  
-   [<span data-ttu-id="3c6ca-123">Pueden que no estén instalados los componentes de Windows</span><span class="sxs-lookup"><span data-stu-id="3c6ca-123">Windows components may not be installed</span></span>](../core/windows-components-may-not-be-installed.md)