---
title: PIP de RosettaNet | Documentos de Microsoft
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
ms.openlocfilehash: 1980f7c5e22259dc6c09d4f2d8dba31f3ac04d61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210796"
---
# <a name="rosettanet-pips"></a>PIP de RosettaNet
La organización RosettaNet crea y mantiene los procesos de interfaz de socio (PIP) para proporcionar las definiciones de procesos empresariales comunes para todos los intercambios de mensajes de RosettaNet.  
  
 Cada especificación de PIP proporciona un archivo de definición (DTD) de tipo de documento y un documento de instrucciones del mensaje. El archivo DTD define la estructura del mensaje de contenido del servicio. El documento de instrucciones de mensaje, que es un archivo HTML legible, especifica las restricciones de nivel de elemento. En conjunto, proporcionan una definición completa del proceso empresarial.  
  
 Para obtener más información acerca de las especificaciones de PIP, vea el sitio RosettaNet Web en [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859).  
  
## <a name="pip-contents"></a>Contenido PIP  
 Una especificación de PIP hace lo siguiente:  
  
-   Describe qué modelo de proceso público implementa  
  
-   Describe cómo configurar el proceso público  
  
-   Proporciona referencias a los documentos que se va a intercambiar en el PIP  
  
 Una especificación de PIP incluye tres componentes principales: una vista operativa de negocios (BOV), vista de servicio funcional (FSV) y una vista de marco de trabajo de implementación (IFV). Cada una de estas vistas especifica las restricciones de nivel de elemento:  
  
-   El BOV especifica la semántica de las entidades de datos empresariales y el flujo de procesos empresariales. Se describen el inicio y estados finales y roles de asociado. Describe la interacción entre los roles y detalles de la seguridad, auditoría y controles de proceso. Especifica los documentos empresariales y entidades de datos profesionales.  
  
-   El FSV especifica las interacciones, agentes y servicios de componentes de red. Proporciona el diseño de componentes de red necesario para ejecutar el PIP y describe las interacciones de componente de red posible.  
  
-   El IFV especifica los formatos de mensaje de protocolo de red y los requisitos de comunicación necesarios para ejecutar el PIP.  
  
## <a name="clusters-and-segments"></a>Clústeres y segmentos  
 Categorizar PIP en una función de negocio de alto nivel (clúster) y una subfunción (segmento). Clústeres y segmentos de organizan los mensajes empresariales en categorías reconocibles. En la tabla siguiente enumera estos clústeres y segmentos.  
  
|Clusters|Segmentos|  
|--------------|--------------|  
|0: compatibilidad con RosettaNet|0a: administrativas<br /><br /> 0c: prueba|  
|1: producto de socios comerciales y revisión de servicio|1a: revisión de socios comerciales<br /><br /> 1b: producto y revisión de servicio|  
|2: obtener información de producto|2a: preparación para la distribución<br /><br /> 2b: notificación de cambio de producto<br /><br /> 2c: información de diseño del producto<br /><br /> 2D: colaboración diseño e ingeniería|  
|3: administración de pedidos|3a: oferta & de entrada de pedidos<br /><br /> 3B: transporte & distribución<br /><br /> 3C: devuelve el identificador & Finanzas<br /><br /> 3D: configuración del producto|  
|4: administración de inventario|4a: previsión colaboración<br /><br /> 4b: asignación de inventario<br /><br /> 4c: informes de inventario<br /><br /> 4d: la reposición del inventario<br /><br /> 4E: informes de ventas<br /><br /> 4F: protección de precios|  
|5: administración de la información de marketing|5a: gestión de oportunidad de clientes potenciales<br /><br /> 5b: administración de campañas de Marketing|  
|6: servicio y soporte técnico|6a: proporcionar y administrar garantías, paquetes de servicio y un contrato de servicios<br /><br /> 6b: proporcionar y administrar la administración de activos (combinado con 6A)<br /><br /> 6c: administración del servicio y soporte técnico|  
|7: fabricación|7a: transferencia de diseño<br /><br /> 7b: administrar fabricación WO & WIP<br /><br /> 7C: distribuir información de fabricación|  
  
 Cada segmento incluye un número de mensaje específico PIP. Por ejemplo, el PIP 3A4 pertenece el grupo de administración de pedidos (clúster 3) y el segmento de oferta y Order Entry (segmento A de clúster 3). Este segmento incluye otros PIP mensaje relacionado, como se indica a continuación:  
  
 Grupo 3: Administración de pedidos  
  
-   Oferta de segmento r: y entrada de pedidos  
  
    -   PIP 3A1: oferta de solicitud  
  
    -   PIP 3A2: solicitud de precio y disponibilidad  
  
    -   PIP 3A3: solicitud de transferencia de carro de la compra  
  
    -   PIP 3A4: administrar el pedido de compra  
  
    -   PIP 3A5: consultar el estado del pedido  
  
    -   PIP 3A6: distribuir el estado del pedido  
  
    -   …  
  
## <a name="see-also"></a>Vea también  
 [RosettaNet y CIDX estándares de mensajería](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [Estándar RNIF](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)