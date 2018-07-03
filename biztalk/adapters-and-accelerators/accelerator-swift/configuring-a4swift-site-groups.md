---
title: Configuración de grupos de sitio de A4SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- site groups, creating
- creating, site groups
- security, user accounts
- user accounts, site groups
- site groups, user accounts
ms.assetid: ec2f3efe-439a-4018-ad94-5ab0fb2808ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f19db0461fc4dc5584fa0774ba0476e3ee471b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969773"
---
# <a name="configuring-a4swift-site-groups"></a>Configuración de grupos de sitio de A4SWIFT
Deberá crear los grupos de sitio correspondiente a bloquear los permisos en las bibliotecas de documentos que se creó durante la configuración de reparación de mensajes y nuevo envío. Para hacer esto con el ejemplo en la sección anterior, un administrador de A4SWIFT podría ir al sitio MRSR y configurar los grupos de sitio siguientes:  
  
- Payments_Creators  
  
- Payments_Repairers  
  
- Payments_Approvers  
  
  Para cada uno de estos grupos de sitio se deben aplicar los permisos siguientes:  
  
- **Ver elementos.** Ver elementos de listas, documentos en bibliotecas de documentos, ver comentarios de discusiones Web y configurar alertas de correo electrónico para las listas.  
  
- **Ver las páginas.** Ver páginas en un sitio Web.  
  
  Para cada usuario que participa en los roles para el departamento de pagos, deberá crear un nuevo usuario del sitio y asignar ese usuario al grupo de sitio que se corresponde con [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] roles creados durante la configuración de MMC.