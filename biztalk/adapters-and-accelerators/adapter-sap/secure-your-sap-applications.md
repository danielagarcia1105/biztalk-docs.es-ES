---
title: Proteger las aplicaciones de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security and protection
ms.assetid: 9f0fb2a2-d6e2-4561-8472-c0bf682a4798
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dade1433b0bd432b53e48da86d53d23be7512de7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005789"
---
# <a name="secure-your-sap-applications"></a>Proteger las aplicaciones de SAP
El sistema SAP puede contener información empresarial confidencial, como los detalles de la cuenta de cliente. Las aplicaciones que usan el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida podría accidentalmente exponerla para tener acceso a los actores no autorizado, a menos que se realizan los esfuerzos para proteger y asegurar los datos durante transmisión. Seguridad y protección de datos normalmente son pensar en los siguientes términos:  
  
- *Autorización* controla el acceso a un recurso basado en la identidad del solicitante.  
  
- *Autenticación* proporciona mecanismos para comprobar la identidad del solicitante.  
  
- *Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.  
  
- *Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, para que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.  
  
  Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que se desarrollan con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Seguridad entre el sistema de SAP y el adaptador](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)
  
-   [Seguridad con el adaptador de SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)
  
-   [Programación segura con el adaptador de SAP](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)
  
-   [Procedimientos recomendados para proteger el adaptador de SAP](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)