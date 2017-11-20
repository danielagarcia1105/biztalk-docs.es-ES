---
title: "Publicar desde la consola de administración de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b78b1981-b227-4cf5-9435-6fc57963552a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 313bfb773a94914ed9bebd3930dfd0033ecf4ac3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a><span data-ttu-id="d7b67-102">Publicar desde la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d7b67-102">Publishing from the BizTalk Server Administration Console</span></span>
<span data-ttu-id="d7b67-103">Si desea administrar la publicación de punto de conexión a través de la [!INCLUDE[prague](../includes/prague-md.md)] consola de administración en lugar del Portal de administración de ESB, puede hacerlo escribiendo un moniker de Universal Description, Discovery y Integration (UDDI) en el campo de descripción de la extremos para publicar en UDDI.</span><span class="sxs-lookup"><span data-stu-id="d7b67-103">If you want to manage endpoint publishing through the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console instead of the ESB Management Portal, you can do so by entering a Universal Description, Discovery, and Integration (UDDI) moniker in the description field of the endpoints to publish to UDDI.</span></span> <span data-ttu-id="d7b67-104">El siguiente es un moniker de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d7b67-104">The following is an example moniker.</span></span>  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 <span data-ttu-id="d7b67-105">Puede establecer las siguientes propiedades UDDI mediante el **descripción** campo el [!INCLUDE[prague](../includes/prague-md.md)] consola de administración:</span><span class="sxs-lookup"><span data-stu-id="d7b67-105">You can set the following UDDI properties using the **Description** field in the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console:</span></span>  
  
-   <span data-ttu-id="d7b67-106">**ModifiedBy**.</span><span class="sxs-lookup"><span data-stu-id="d7b67-106">**ModifiedBy**.</span></span> <span data-ttu-id="d7b67-107">Esta propiedad opcional contiene el nombre de cuenta del usuario que modificó el punto de conexión; Por ejemplo, MyDomainName\MyUserName.</span><span class="sxs-lookup"><span data-stu-id="d7b67-107">This optional property contains the account name of the user that modified the endpoint; for example, MyDomainName\MyUserName.</span></span>  
  
-   <span data-ttu-id="d7b67-108">**UDDIContact**.</span><span class="sxs-lookup"><span data-stu-id="d7b67-108">**UDDIContact**.</span></span> <span data-ttu-id="d7b67-109">Esta propiedad opcional es el nombre de contacto del usuario definido para el proveedor de negocio de UDDI.</span><span class="sxs-lookup"><span data-stu-id="d7b67-109">This optional property is the contact name of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="d7b67-110">**UDDIUserType**.</span><span class="sxs-lookup"><span data-stu-id="d7b67-110">**UDDIUserType**.</span></span> <span data-ttu-id="d7b67-111">Esta propiedad opcional es el tipo de usuario del usuario definido para el proveedor de negocio de UDDI.</span><span class="sxs-lookup"><span data-stu-id="d7b67-111">This optional property is the user type of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="d7b67-112">**UDDIEmail**.</span><span class="sxs-lookup"><span data-stu-id="d7b67-112">**UDDIEmail**.</span></span> <span data-ttu-id="d7b67-113">Esta propiedad opcional es la dirección de correo electrónico del usuario definido para el proveedor de negocio de UDDI.</span><span class="sxs-lookup"><span data-stu-id="d7b67-113">This optional property is the e-mail address of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="d7b67-114">**TransportType**.</span><span class="sxs-lookup"><span data-stu-id="d7b67-114">**TransportType**.</span></span> <span data-ttu-id="d7b67-115">Esta propiedad opcional es el tipo de adaptador de punto de conexión, como **archivo, MQS, WCF-WsHttp, SOAP, HTTP,** o **FTP**.</span><span class="sxs-lookup"><span data-stu-id="d7b67-115">This optional property is the endpoint adapter type, such as **FILE, MQS, WCF-WsHttp, SOAP, HTTP,** or **FTP**.</span></span>  
  
-   <span data-ttu-id="d7b67-116">**Estado**.</span><span class="sxs-lookup"><span data-stu-id="d7b67-116">**Status**.</span></span> <span data-ttu-id="d7b67-117">Esta propiedad opcional es el estado del punto de conexión, como **publicada** o **pendiente**.</span><span class="sxs-lookup"><span data-stu-id="d7b67-117">This optional property is the status of the endpoint, such as **Published** or **Pending**.</span></span> <span data-ttu-id="d7b67-118">El servicio de publicación de UDDI usa este atributo para detectar el estado del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d7b67-118">The UDDI Publishing Service uses this attribute to discover the status of the endpoint.</span></span>  
  
-   <span data-ttu-id="d7b67-119">**BindingType**.</span><span class="sxs-lookup"><span data-stu-id="d7b67-119">**BindingType**.</span></span> <span data-ttu-id="d7b67-120">Esta propiedad opcional es el protocolo específico (tipo de dirección URL) que admite el enlace de UDDI, como **mailto, http, https, ftp, fax, teléfono,** o **otros**.</span><span class="sxs-lookup"><span data-stu-id="d7b67-120">This optional property is the specific protocol (URL Type) that the UDDI binding supports, such as **mailto, http, https, ftp, fax, phone,** or **other**.</span></span> <span data-ttu-id="d7b67-121">El servicio de publicación de UDDI usa este atributo para crear el enlace de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d7b67-121">The UDDI Publishing Service uses this attribute to create the endpoint binding.</span></span>