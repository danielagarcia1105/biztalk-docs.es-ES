---
title: Huella digital del certificado de servicio no válida | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22e7d74e-40ec-4187-9246-bc8da2a9ce86
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a465d631e72bc27c6b24274deb31e396037aa182
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257220"
---
# <a name="invalid-service-certificate-thumbprint"></a>Huella digital de certificado de servicio no válida
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Huella digital de certificado de servicio no válida; se esperaban 40 dígitos hexadecimales.|  
  
## <a name="explanation"></a>Explicación  
 Se especificó una huella digital de certificado de servicio no válida.  
  
## <a name="user-action"></a>Acción del usuario  
 En el código que configura el puerto WCF, la propiedad de certificado de servicio de la interfaz de usuario espera un valor de 40 dígitos hexadecimales. Ejemplo: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39  
  
 Para obtener más información sobre certificados, vea el recurso siguiente:  
  
-   [Instalación de certificados para los adaptadores de WCF](../core/installing-certificates-for-the-wcf-adapters.md)