---
title: PIP de RosettaNet | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, clusters
- RosettaNet, PIPs
- PIPs, PIP specifications
- PIPs, segments
- PIPs, RosettaNet
- DTDs, DTD files
ms.assetid: 2f7e8db3-9ccb-403a-9fe7-58fbba3c4cb1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8891979352ce47e18c8cfda80162b3683002c6f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989253"
---
# <a name="rosettanet-pips"></a>PIP de RosettaNet
La organización RosettaNet crea y mantiene los procesos de interfaz de socio (PIP) para proporcionar las definiciones de procesos empresariales comunes para todos los intercambios de mensajes de RosettaNet.  
  
 Cada especificación de PIP proporciona un archivo de definición (DTD) de tipo de documento y un documento de guía de mensaje. El archivo DTD define la estructura del mensaje de contenido del servicio. El documento de instrucciones del mensaje, que es un archivo HTML legible, especifica las restricciones de nivel de elemento. Juntos, proporcionan una definición completa del proceso empresarial.  
  
 Para obtener más información acerca de las especificaciones de PIP, vea el sitio RosettaNet Web en [ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=33859).  
  
## <a name="pip-contents"></a>Contenido PIP  
 Una especificación de PIP hace lo siguiente:  
  
- Describe qué modelo de proceso público implementa  
  
- Describe cómo configurar el proceso público  
  
- Proporciona referencias a los documentos que se van a intercambiar dentro del PIP  
  
  Una especificación de PIP incluye tres partes principales: vista operativa de negocio (BOV), vista de servicio funcional (FSV) y una vista de marco de trabajo de implementación (IFV). Cada una de estas vistas especifica restricciones de nivel de elemento:  
  
- El BOV especifica la semántica de las entidades de datos empresariales y el flujo de procesos empresariales. Describe el inicio y estados finales y roles de asociado. Describe la interacción entre los roles y detalles de la seguridad, auditoría y controles del proceso. Especifica los documentos empresariales y las entidades de datos empresariales.  
  
- El FSV especifica las interacciones, agentes y servicios de componentes de red. Proporciona el diseño del componente de red necesario para ejecutar el PIP y se describen las interacciones del componente de red posible.  
  
- El IFV especifica los formatos de mensaje de protocolo de red y los requisitos de comunicación necesarios para ejecutar el PIP.  
  
## <a name="clusters-and-segments"></a>Clústeres y segmentos  
 Clasifique PIP por una función de negocio de alto nivel (clúster) y una subfunción (segmento). Clústeres y segmentos de organizan los mensajes empresariales en categorías reconocibles. En la tabla siguiente se enumera estos segmentos y clústeres.  
  
|Clusters|Segmentos|  
|--------------|--------------|  
|0: soporte técnico de RosettaNet|0a: administrativas<br /><br /> 0c: pruebas|  
|1: revisión de servicios y productos de asociados|1a: revisión de asociados<br /><br /> 1b: revisión de servicios y productos|  
|2: información del producto|2a: preparación para la distribución<br /><br /> 2b: notificación de cambio de producto<br /><br /> 2c: información de diseño del producto<br /><br /> 2D: colaboración diseño e ingeniería|  
|3: administración de pedidos|3a: oferta & entrada de pedidos<br /><br /> 3B: transporte de & distribución<br /><br /> 3C: devuelve y finanzas<br /><br /> 3D: configuración del producto|  
|4: administración del inventario|4a: previsión de colaboración<br /><br /> 4b: asignación de inventario<br /><br /> 4c: informes de inventario<br /><br /> 4d: la reposición del inventario<br /><br /> 4E: informes de ventas<br /><br /> 4F: protección de precios|  
|5: administración de la información de marketing|5a: administración de oportunidades de clientes potenciales<br /><br /> 5b: administración de campañas de Marketing|  
|6: servicio y soporte técnico|6a: proporcionar y administrar las garantías, paquetes de servicio y contrato de servicios<br /><br /> 6b: proporcionar y administrar la administración de activos (combinada con 6A)<br /><br /> 6c: soporte técnico y administración de servicios|  
|7: de fabricación|7a: transferencia de diseño<br /><br /> 7b: administrar fabricación WO & WIP<br /><br /> 7C: distribuir información de fabricación|  
  
 Cada segmento incluye una serie de PIP de mensaje específico. Por ejemplo, el PIP de 3A4 es una parte del clúster de administración de pedidos (clúster de 3) y el segmento de oferta y entrada de pedidos (segmento una del clúster de 3). Este segmento incluye otros PIP mensajes relacionados, como sigue:  
  
 Clúster de 3: Administración de pedidos  
  
-   Segmento r: Quote y entrada de pedidos  
  
    -   PIP 3A1: oferta de solicitud  
  
    -   PIP 3A2: solicitud de precio y disponibilidad  
  
    -   PIP 3A3: solicitud de transferencia de carro de la compra  
  
    -   PIP 3A4: administrar pedido de compra  
  
    -   PIP 3A5: consultar el estado del pedido  
  
    -   PIP 3A6: distribuir el estado del pedido  
  
    -   …  
  
## <a name="see-also"></a>Vea también  
 [RosettaNet y CIDX estándares de mensajería](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [Estándar RNIF](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)