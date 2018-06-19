---
title: Cómo configurar certificados para la resolución de entidades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 060101c1-14f3-4600-a18e-48a160d59bca
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 153c8ccce1fafbe32c51b1c048fad4081f5b0b0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297724"
---
# <a name="how-to-configure-certificates-for-party-resolution"></a>Cómo configurar certificados para la resolución de entidades
Al usar el Explorador de BizTalk para configurar una entidad, puede configurar la entidad para que la entidad se resuelve mediante la firma digital. Si configura la entidad de esta manera, cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje, usará el certificado de clave pública para determinar quién envió el mensaje y para resolver el remitente para una entidad conocida en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe iniciar sesión como un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  
  
### <a name="to-configure-party-resolution-to-use-a-certificate"></a>Para configurar la resolución de entidades para utilizar un certificado  
  
1.  Abra la **propiedades de la entidad** cuadro de diálogo.  
  
2.  Haga clic en el **certificado** ficha y, a continuación, haga clic en **examinar**.  
  
3.  Seleccione un certificado.  
  
4.  Haga clic en **Aceptar**.