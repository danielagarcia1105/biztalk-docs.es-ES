---
title: "Configuración de grupos de sitio de A4SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- site groups, creating
- creating, site groups
- security, user accounts
- user accounts, site groups
- site groups, user accounts
ms.assetid: ec2f3efe-439a-4018-ad94-5ab0fb2808ee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0070f10819ebbde18cdeab9c3bd534ca74bfbcd9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a4swift-site-groups"></a>Configuración de grupos de sitio de A4SWIFT
Debe crear los grupos de sitio correspondiente para restringir los permisos en las bibliotecas de documentos que se crearon durante la configuración de reparación de mensajes y nuevo envío. Para realizar esta acción con el ejemplo en la sección anterior, un administrador de A4SWIFT ¿vaya al sitio MRSR y configurar los grupos de sitio siguientes:  
  
-   Payments_Creators  
  
-   Payments_Repairers  
  
-   Payments_Approvers  
  
 Para cada uno de estos grupos de sitio se deben aplicar los permisos siguientes:  
  
-   **Ver elementos.** Ver elementos en listas, documentos en bibliotecas de documentos, ver comentarios de discusión Web y configurar alertas de correo electrónico para las listas.  
  
-   **Páginas de vista.** Ver páginas en un sitio Web.  
  
 Para cada usuario que participa en los roles para el departamento de pagos, debe crear un nuevo usuario del sitio y asignar ese usuario al grupo de sitio que se corresponde con [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] roles que se crearon durante la configuración de MMC.