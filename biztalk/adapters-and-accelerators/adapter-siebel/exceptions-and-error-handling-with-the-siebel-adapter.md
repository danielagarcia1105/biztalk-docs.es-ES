---
title: Excepciones y control de errores con el adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error handling, troubleshooting
- exceptions, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: d46e908f-0715-43e2-879b-f5d0beb9bc64
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67a615bec1bf1b8cd29e84728f39d6fea626f16e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977124"
---
# <a name="exceptions-and-error-handling-with-the-siebel-adapter"></a><span data-ttu-id="b37f1-102">Excepciones y control de errores con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="b37f1-102">Exceptions and Error Handling with the Siebel adapter</span></span>
## <a name="exception-list"></a><span data-ttu-id="b37f1-103">Lista de excepciones</span><span class="sxs-lookup"><span data-stu-id="b37f1-103">Exception list</span></span>
<span data-ttu-id="b37f1-104">Las excepciones producidas por la [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b37f1-104">The exceptions thrown by the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span> <span data-ttu-id="b37f1-105">Estos pueden contener:</span><span class="sxs-lookup"><span data-stu-id="b37f1-105">These can contain:</span></span>  
  
- <span data-ttu-id="b37f1-106">Una excepción interna, que es una excepción del sistema que se produce en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b37f1-106">An inner exception, which is a system exception that the .NET Framework throws</span></span>  
  
- <span data-ttu-id="b37f1-107">Una excepción de LOB que inicia la biblioteca de cliente de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="b37f1-107">An LOB exception that the LOB client library throws.</span></span>  
  
  <span data-ttu-id="b37f1-108">Para obtener más información acerca de la excepción interna, consulte la documentación de .NET Framework o Siebel respectiva.</span><span class="sxs-lookup"><span data-stu-id="b37f1-108">For more information about the inner exception, refer to the respective .NET Framework or Siebel documentation.</span></span> <span data-ttu-id="b37f1-109">La excepción también contiene un mensaje de error detallado que ayuda a resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="b37f1-109">The exception also contains a detailed error message that helps in resolving the problem.</span></span> <span data-ttu-id="b37f1-110">Tenga en cuenta que la lista de excepciones que se mencionan aquí no es completa.</span><span class="sxs-lookup"><span data-stu-id="b37f1-110">Note that the list of exceptions mentioned here is not comprehensive.</span></span>  
  
|<span data-ttu-id="b37f1-111">Excepción</span><span class="sxs-lookup"><span data-stu-id="b37f1-111">Exception</span></span>|<span data-ttu-id="b37f1-112">Descripción de la posible causa/Error</span><span class="sxs-lookup"><span data-stu-id="b37f1-112">Possible Cause/Error Description</span></span>|  
|---------------|---------------------------------------|  
|<span data-ttu-id="b37f1-113">ConnectionException</span><span class="sxs-lookup"><span data-stu-id="b37f1-113">ConnectionException</span></span>|<span data-ttu-id="b37f1-114">El adaptador produce esta excepción si no puede establecer una conexión o cerrar una conexión existente a un sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="b37f1-114">The adapter throws this exception if it is unable to establish a connection or close an existing connection to a Siebel system.</span></span>|  
|<span data-ttu-id="b37f1-115">CredentialsException</span><span class="sxs-lookup"><span data-stu-id="b37f1-115">CredentialsException</span></span>|<span data-ttu-id="b37f1-116">El adaptador produce esta excepción si el cliente del adaptador no especifica un nombre de usuario o contraseña para conectarse a un sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="b37f1-116">The adapter throws this exception if the adapter client does not specify a user name or password to connect to a Siebel system.</span></span>|  
|<span data-ttu-id="b37f1-117">MetadataException</span><span class="sxs-lookup"><span data-stu-id="b37f1-117">MetadataException</span></span>|<span data-ttu-id="b37f1-118">El adaptador produce esta excepción si se produce un error al recuperar metadatos para artefactos de Siebel.</span><span class="sxs-lookup"><span data-stu-id="b37f1-118">The adapter throws this exception if it fails to retrieve metadata for Siebel artifacts.</span></span>|  
|<span data-ttu-id="b37f1-119">XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="b37f1-119">XmlReaderParsingException</span></span>|<span data-ttu-id="b37f1-120">El adaptador produce esta excepción si la información de entrada proporcionada por los clientes del adaptador para invocar una operación en el sistema de Siebel, está incompleta o incorrecta.</span><span class="sxs-lookup"><span data-stu-id="b37f1-120">The adapter throws this exception if the input information provided by the adapter clients to invoke an operation in the Siebel system, is either incomplete or incorrect.</span></span>|  
|<span data-ttu-id="b37f1-121">XmlReaderGenerationException</span><span class="sxs-lookup"><span data-stu-id="b37f1-121">XmlReaderGenerationException</span></span>|<span data-ttu-id="b37f1-122">El adaptador produce esta excepción si no puede generar la salida para una operación que se ejecuta en un sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="b37f1-122">The adapter throws this exception if it is unable to generate output for an operation executed in a Siebel system.</span></span>|  
|<span data-ttu-id="b37f1-123">TargetSystemException</span><span class="sxs-lookup"><span data-stu-id="b37f1-123">TargetSystemException</span></span>|<span data-ttu-id="b37f1-124">El adaptador produce esta excepción si la API de COM de Siebel, que el adaptador utiliza para interactuar con el sistema de Siebel, inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="b37f1-124">The adapter throws this exception if the Siebel COM API, which the adapter uses to interface with the Siebel system, throws an exception.</span></span> <span data-ttu-id="b37f1-125">La excepción interna contiene la excepción producida por la API de COM de Siebel.</span><span class="sxs-lookup"><span data-stu-id="b37f1-125">The inner exception contains the exception thrown by the Siebel COM API.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b37f1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b37f1-126">See Also</span></span>  
 <span data-ttu-id="b37f1-127">[Comprender el adaptador de BizTalk para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md) </span><span class="sxs-lookup"><span data-stu-id="b37f1-127">[Understand BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md) </span></span>  
[<span data-ttu-id="b37f1-128">Solucionar problemas del adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="b37f1-128">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)