---
title: Restricciones en el protocolo SMTP a la propiedad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: c876d30e-44ab-462d-8c98-64416ed6dd1f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b59495ac94b3591801101607533eb9c7dba158fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268340"
---
# <a name="restrictions-on-the-smtp-to-property"></a>Restricciones en el protocolo SMTP a la propiedad
El **a** propiedad es una cadena que especifica la dirección SMTP del destinatario del mensaje. Puede incluir varias direcciones con un separador admitido por el servidor SMTP.  
  
 No hay restricciones específicas de formato en las direcciones SMTP. Esto significa que el adaptador aceptará cualquier formato admitido por un servidor SMTP. Si un usuario proporciona direcciones que no son válidas, la operación de envío fallará, y el adaptador de envío SMTP informará de un error.  
  
 Las únicas restricciones para esta propiedad son que no puede dejarse en blanco y que no puede contener más de 256 caracteres.  
  
## <a name="see-also"></a>Vea también  
 [Restricciones al configurar el adaptador de SMTP](../core/restrictions-when-configuring-the-smtp-adapter.md)