---
title: "Apéndice B: mediante la aplicación PeopleSoft | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PeopleSoft, using
- using PeopleSoft application
ms.assetid: 36475836-1d23-4bb4-a3c1-cdd3fff28476
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ff5c7b2b15c709064174371f1fcab9beb95e42d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-b-using-the-peoplesoft-application"></a><span data-ttu-id="d5f26-102">Apéndice B: utilizando la aplicación PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="d5f26-102">Appendix B: Using the PeopleSoft Application</span></span>
<span data-ttu-id="d5f26-103">En esta sección se describe el uso de diferentes áreas de PeopleSoft que pueden ser útiles en la prueba de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="d5f26-103">This section describes using different areas of PeopleSoft that could be useful in your orchestration testing.</span></span>  
  
 <span data-ttu-id="d5f26-104">Cuando use PeopleSoft para puertos de recepción, use PeopleTools para crear un documento XML.</span><span class="sxs-lookup"><span data-stu-id="d5f26-104">When you use PeopleSoft for receive ports, you use PeopleTools to create an XML document.</span></span> <span data-ttu-id="d5f26-105">No se necesita nada especial para interactuar con PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="d5f26-105">Nothing special is required to interact with PeopleSoft.</span></span> <span data-ttu-id="d5f26-106">Para un evento, debe ser capaz de obtener acceso a un **http\\\\:\<host >:\<puerto >** para realizar escuchas de eventos de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="d5f26-106">For an event, you must be able to access to an **http\\\\:\<host>:\<port>** to listen for events from PeopleSoft.</span></span> <span data-ttu-id="d5f26-107">Si tiene disponibles un host y un puerto, podrá configurar un host y un puerto HTTP específicos configurando PeopleSoft Integration Broker.</span><span class="sxs-lookup"><span data-stu-id="d5f26-107">If a host and port is not available to you, you can set up a specific HTTP host and port by configuring the PeopleSoft Integration Broker.</span></span>  
  
 <span data-ttu-id="d5f26-108">Para completar la prueba de un PeopleSoft de puerto de recepción [generar XML o esquema en PeopleSoft](../core/generating-xml-or-schema-in-peoplesoft.md) explica cómo desencadenar un evento de PeopleSoft cambiando algo en un entorno de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="d5f26-108">To complete the testing of a PeopleSoft receive port, [Generating XML or Schema in PeopleSoft](../core/generating-xml-or-schema-in-peoplesoft.md) discusses how to trigger a PeopleSoft event by changing something in a PeopleSoft environment.</span></span> <span data-ttu-id="d5f26-109">El cambio activa un archivo XML que se envía a la carpeta que configuró en la orquestación que se debe supervisar.</span><span class="sxs-lookup"><span data-stu-id="d5f26-109">The change activates an XML file that is sent to the folder you set in the orchestration to be monitored.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5f26-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d5f26-110">In This Section</span></span>  
  
-   [<span data-ttu-id="d5f26-111">Generar XML o esquema en PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="d5f26-111">Generating XML or Schema in PeopleSoft</span></span>](../core/generating-xml-or-schema-in-peoplesoft.md)  
  
-   [<span data-ttu-id="d5f26-112">Crear un Host de HTTP de PeopleSoft y puerto</span><span class="sxs-lookup"><span data-stu-id="d5f26-112">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)