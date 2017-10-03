---
title: "Defensa contra los ataques por denegación de servicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, denial-of-service attacks
- denial-of-service attacks
ms.assetid: 63342d7a-a5df-4e11-9037-93175d8f7ea7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 667b9d321f7703f770297b001ef2a99be2bf4902
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="defending-against-denial-of-service-attacks"></a>Defensa contra los ataques por denegación de servicio
Un usuario puede iniciar un ataque de denegación de servicio en una instalación de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] agotando el RNIFReceive.aspx de página de recepción. Puede hacerlo mediante el envío de grandes cantidades de mensajes vacíos a esa página. Si no está activada, este tipo de ataque podría saturar el registro de eventos con eventos publicados por el ASPX izquierda recibe la página.  
  
## <a name="defending-against-an-attack"></a>Defensa contra un ataque  
 Para proteger el servidor contra los ataques de denegación de servicio, se recomienda que mantenga el registro de eventos con un tamaño razonable y tomar medidas para tratar con un número excesivo de eventos. Puede hacerlo estableciendo el tamaño máximo del registro, seleccionando una manera de sobrescribir eventos o usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) para administrar el tamaño del registro. Para obtener más información, consulte la ayuda para [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md)