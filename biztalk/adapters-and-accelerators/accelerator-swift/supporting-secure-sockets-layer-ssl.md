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
---
# <a name="supporting-secure-sockets-layer-ssl"></a>Compatibilidad con capa de Sockets seguros (SSL)
Para implementar el protocolo de capa de Sockets seguros (SSL) en la implementación entre los equipos cliente y los servidores MRSR, es necesario solicitar y configurar un certificado de "Autenticación de servidor" en los servidores de Internet Information Services (IIS).  
  
 Un certificado debe utilizarse para todos los servidores en el clúster de equilibrio de carga de red (NLB). Debe asegurarse de que el nombre utilizado en la solicitud de certificado es el nombre de host virtual en lugar de un nombre de servidor individuales.