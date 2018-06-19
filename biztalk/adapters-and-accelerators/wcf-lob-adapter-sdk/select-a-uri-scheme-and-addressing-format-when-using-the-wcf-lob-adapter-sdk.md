---
title: Seleccione un esquema de URI y el formato de direccionamiento al usar el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb4feee-3d39-43ca-82ac-aba38c13bc69
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9990facf6a23f4abea37ee9ce9758a7333eaca61
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965314"
---
# <a name="select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="6b465-102">Seleccione un esquema de URI y el formato de direccionamiento al usar el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="6b465-102">Select a URI scheme and addressing format when using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="6b465-103">Un identificador uniforme de recursos (URI) identifica de forma única recursos como un servicio Web o, en el caso de un adaptador que se desarrollan con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], el sistema al que conectarse, así como la acción que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="6b465-103">A Uniform Resource Identifier (URI) uniquely identifies resources like a Web service or, in the case of an adapter developed with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], the system to connect to as well as the action to perform.</span></span> <span data-ttu-id="6b465-104">Esta sección proporciona una recomendación sobre cómo construir un URI para describir de forma exclusiva la dirección del extremo y la acción para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="6b465-104">This section provides a recommendation on how to construct a URI to uniquely describe the endpoint address and the action for your adapter.</span></span>  
  
## <a name="anatomy-of-a-uri"></a><span data-ttu-id="6b465-105">Anatomía de un identificador URI</span><span class="sxs-lookup"><span data-stu-id="6b465-105">Anatomy of a URI</span></span>  
 <span data-ttu-id="6b465-106">Un URI consta de los tres componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="6b465-106">A URI consists of the following three components:</span></span>  
  
-   <span data-ttu-id="6b465-107">**Nombre de esquema** es la parte inicial de la cadena de URI y es el primer nivel de la estructura de nomenclatura; algunos ejemplos son http, urn y contoso.</span><span class="sxs-lookup"><span data-stu-id="6b465-107">**Scheme name** is the lead part of the URI string and is the first level of the naming structure; examples include http, urn, and contoso.</span></span>  
  
-   <span data-ttu-id="6b465-108">**Parte jerárquica** consta de información que es normalmente jerárquico y puede contener autoridad opcional, el nombre de host y la información del puerto.</span><span class="sxs-lookup"><span data-stu-id="6b465-108">**Hierarchical part** consists of information that is usually hierarchical and can contain optional authority, hostname, and port information.</span></span> <span data-ttu-id="6b465-109">Algunos ejemplos son el nombre de usuario y www.microsoft.com =User@microsoft.com:4099.</span><span class="sxs-lookup"><span data-stu-id="6b465-109">Examples include www.microsoft.com and UserName=User@microsoft.com:4099.</span></span>  
  
-   <span data-ttu-id="6b465-110">**Consulta** contiene la información opcional marcados con un signo de interrogación (?) y normalmente se agrupan como pares de clave/valor separados por una y comercial (&).</span><span class="sxs-lookup"><span data-stu-id="6b465-110">**Query** contains optional information marked with a question mark (?) and typically grouped as key/value pairs separated by an ampersand (&).</span></span> <span data-ttu-id="6b465-111">Por ejemplo, contoso://microsoft.com/functions?name=Find.</span><span class="sxs-lookup"><span data-stu-id="6b465-111">For example, contoso://microsoft.com/functions?name=Find.</span></span>  
  
-   <span data-ttu-id="6b465-112">**Fragmento** se utiliza para almacenar información de identificación adicional que pueda ser necesaria para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="6b465-112">**Fragment** is used to store extra identifying information that may be needed by the adapter.</span></span> <span data-ttu-id="6b465-113">El fragmento se separa con una almohadilla (#); Por ejemplo, contoso://microsoft.com/functions?name=Find#public.</span><span class="sxs-lookup"><span data-stu-id="6b465-113">The fragment is separated by a hash (#); for example, contoso://microsoft.com/functions?name=Find#public.</span></span>  
  
 <span data-ttu-id="6b465-114">No se pueden usar todas las características proporcionadas por la sintaxis del URI.</span><span class="sxs-lookup"><span data-stu-id="6b465-114">You might not use all of the features provided by the URI syntax.</span></span>  
  
## <a name="designing-the-uri"></a><span data-ttu-id="6b465-115">Diseñar el URI</span><span class="sxs-lookup"><span data-stu-id="6b465-115">Designing the URI</span></span>  
 <span data-ttu-id="6b465-116">Como programador de adaptadores, tendrá que idear un URI adecuado para el sistema de línea de negocio de destino.</span><span class="sxs-lookup"><span data-stu-id="6b465-116">As an adapter developer, you will have to devise an appropriate URI for your target line-of-business system.</span></span> <span data-ttu-id="6b465-117">Al diseñar su URI, es importante para que sea único y descriptivo.</span><span class="sxs-lookup"><span data-stu-id="6b465-117">When designing your URI, it is important to make it unique and meaningful.</span></span>  
  
 <span data-ttu-id="6b465-118">Un URI único es aquel que no entra en conflicto con URI existentes dentro de una organización y a través de otras empresas e Internet.</span><span class="sxs-lookup"><span data-stu-id="6b465-118">A unique URI is one that does not conflict with existing URIs within an organization and across other businesses and the Internet.</span></span> <span data-ttu-id="6b465-119">Por ejemplo, al elegir un nombre de esquema como "http" o "afs" que ya utiliza mucho podría producir conexión o problemas de funcionamiento porque se pueden enrutar las solicitudes a un sistema diferente y no a su adaptador o puede ser reconoce actualmente.</span><span class="sxs-lookup"><span data-stu-id="6b465-119">For example, choosing a scheme name like "http" or "afs" that may be currently recognized or already in wide use could cause connection or operational problems because requests might be routed to a different system and not to your adapter.</span></span>  
  
 <span data-ttu-id="6b465-120">Otro aspecto importante del diseño URI es conseguir que sea significativo para la audiencia de desarrolladores que usará el adaptador.</span><span class="sxs-lookup"><span data-stu-id="6b465-120">Another important aspect of URI design is making it meaningful to the developer audience who will be consuming your adapter.</span></span> <span data-ttu-id="6b465-121">Por ejemplo, si va a escribir un adaptador para el sistema de procesamiento de notificaciones de un médico, podría diseñar un esquema de URI que incluye el nombre de su compañía, el procesamiento nombre del sistema y la versión del sistema de reclamaciones de destino: northwind.contoso.cps.v1.0://.</span><span class="sxs-lookup"><span data-stu-id="6b465-121">For example, if you are writing an adapter for a medical claims processing system, you could design a URI scheme that includes your company name, the target claims processing system name, and system version: northwind.contoso.cps.v1.0://.</span></span>  
  
## <a name="connecting-to-the-target-system"></a><span data-ttu-id="6b465-122">Conectarse al sistema de destino</span><span class="sxs-lookup"><span data-stu-id="6b465-122">Connecting to the Target System</span></span>  
 <span data-ttu-id="6b465-123">Cadenas de conexión presentan la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="6b465-123">Connection strings have the following syntax:</span></span>  
  
 <span data-ttu-id="6b465-124">**\<esquema\>: //[userinfo "@"]\<LOB cadena de conexión\>**</span><span class="sxs-lookup"><span data-stu-id="6b465-124">**\<scheme\>://[userinfo "@"]\<LOB Connection String\>**</span></span>  
  
 <span data-ttu-id="6b465-125">Por ejemplo, puede conectarse al catálogo de contoso (una línea de ejemplo de aplicación de negocio) del sistema de pedidos con los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6b465-125">For example, you could connect to the contoso catalog ordering system (a sample line of business application) using the following:</span></span>  
  
 <span data-ttu-id="6b465-126">**¿Northwind.contoso.v1.0://\<servername\>? Catálogo = Contoso & Integrated Security = True**</span><span class="sxs-lookup"><span data-stu-id="6b465-126">**northwind.contoso.v1.0://\<servername\>?Catalog=Contoso&Integrated Security=True**</span></span>  
  
 <span data-ttu-id="6b465-127">También puede proporcionar información de la entidad opcional en el URI incluido el nombre de usuario y contraseña y otras credenciales importantes.</span><span class="sxs-lookup"><span data-stu-id="6b465-127">You can also provide optional authority information in the URI including user name and password and other important credentials.</span></span> <span data-ttu-id="6b465-128">Sin embargo, esto puede suponer un riesgo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6b465-128">However, this can present a security risk.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6b465-129">No pase las credenciales de usuario y otra información confidencial en el URI.</span><span class="sxs-lookup"><span data-stu-id="6b465-129">Do not pass user credentials and other sensitive information in the URI.</span></span> <span data-ttu-id="6b465-130">Esta información se puede interceptar y ver los usuarios no autorizados.</span><span class="sxs-lookup"><span data-stu-id="6b465-130">This information could be intercepted and viewed by unauthorized users.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b465-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b465-131">See Also</span></span>  
 [<span data-ttu-id="6b465-132">Planear y diseñar un adaptador mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="6b465-132">Plan and design an adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)