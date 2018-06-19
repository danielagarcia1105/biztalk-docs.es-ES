---
title: Admitir Secure Sockets Layer (SSL) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSL
ms.assetid: 012a5be0-bab8-4a60-9d63-b9684b91e4a7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 086ec1715d76a25649cb2285b31b3df790b0fe3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214164"
---
# <a name="supporting-secure-sockets-layer-ssl"></a><span data-ttu-id="5c991-102">Compatibilidad con capa de Sockets seguros (SSL)</span><span class="sxs-lookup"><span data-stu-id="5c991-102">Supporting Secure Sockets Layer (SSL)</span></span>
<span data-ttu-id="5c991-103">Para implementar el protocolo de capa de Sockets seguros (SSL) en la implementación entre los equipos cliente y los servidores MRSR, es necesario solicitar y configurar un certificado de "Autenticación de servidor" en los servidores de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="5c991-103">To implement the Secure Sockets Layer (SSL) protocol in your deployment between the client computers and the MRSR servers, you need to request and configure a "Server Authentication" certificate on your Internet Information Services (IIS) servers.</span></span>  
  
 <span data-ttu-id="5c991-104">Un certificado debe utilizarse para todos los servidores en el clúster de equilibrio de carga de red (NLB).</span><span class="sxs-lookup"><span data-stu-id="5c991-104">One certificate should be used for all the servers in your Network Load Balancing (NLB) cluster.</span></span> <span data-ttu-id="5c991-105">Debe asegurarse de que el nombre utilizado en la solicitud de certificado es el nombre de host virtual en lugar de un nombre de servidor individuales.</span><span class="sxs-lookup"><span data-stu-id="5c991-105">You should ensure that the name used in the certificate request is the virtual host name instead of an individual server name.</span></span>