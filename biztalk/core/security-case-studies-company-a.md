---
title: "Casos prácticos de seguridad: La compañía A | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, examples
- security, architecture
- architecture, security
- security, case studies
ms.assetid: 9417ecf9-e340-479f-b120-552c62f3b189
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c1f48edfc2ab2228d910a0729025fd7b4da117f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-case-studies-company-a"></a>Casos prácticos de seguridad: La compañía A
La compañía A es un importante proveedor de material y servicios para la industria. Su modelo de negocio se basa en transacciones electrónicas con proveedores y clientes clave. La compañía A usa una aplicación de Microsoft BizTalk para administrar las transacciones y las comunicaciones entre los entornos internos y externos.  
  
## <a name="potential-threats-and-security-concerns"></a>Aspectos relacionados con la seguridad y posibles amenazas  
 La compañía A quiere asegurarse de que sólo va a procesar mensajes cuyo origen esté autenticado. Algunos de los documentos que procesa BizTalk Server pueden contener información confidencial, como datos de finanzas y personal. La compañía A comprueba todos los mensajes entrantes utilizando interfaces API criptográficas y personalizadas. Además, ha diseñado su arquitectura física para controlar sus necesidades de seguridad.  
  
 La compañía A utiliza el protocolo de transferencia de archivos (FTP) para una parte del tráfico de mensajes. Aunque la falta de seguridad es inherente al protocolo FTP, la compañía A acepta los riesgos asociados a su utilización porque dispone de varios servidores de seguridad para proteger las aplicaciones que se comunican con el exterior. Como la compañía A recibe una parte de los datos entrantes a través de HTTPS, le preocupan los ataques de denegación de servicio procedentes del exterior. Si se produce un ataque de denegación de servicio, la compañía dispone de mecanismos para avisar a las personas interesadas inmediatamente.  
  
## <a name="security-architecture"></a>Arquitectura de seguridad  
 En la ilustración siguiente, se muestra la arquitectura de seguridad que utiliza la compañía A. Observe que el entorno se ha segmentado mediante servidores de seguridad para proteger la aplicación para el usuario y los servidores de contenido, los servidores de lógica de negocios y de base de datos de servidor, y la infraestructura de mensajes salientes.  
  
 **Figura 1 arquitectura de seguridad de la compañía A**  
  
 ![Una arquitectura de seguridad de la compañía](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")  
  
 La compañía A dispone de dos métodos principales para enviar información al servidor BizTalk Server y para recibirla de éste. El primer método utiliza FTP. La compañía A admite las transacciones de intercambio de datos electrónicos (EDI) utilizando un proveedor de servicio de traducción de terceros para comunicarse con sus proveedores y socios. Este servicio de traducción de terceros controla los pedidos entrantes y salientes que BizTalk Server tiene que procesar en el formato EDI.  
  
 El segundo método que utiliza la compañía A es HTTPS. La compañía A también trabaja con un proveedor de servicios de terceros que sirve de concentrador del sector y que compra y vende los productos que la compañía A vende y consume con mayor facilidad.  
  
## <a name="secure-digital-certificates"></a>Certificados digitales seguros  
 La compañía A implementa sus propios certificados digitales seguros. Sólo administra unos pocos certificados. Puesto que se sirve para ello de un proveedor de servicios de terceros, no le da mucha importancia a esta actividad. La compañía A es consciente de que los certificados digitales son un motivo de preocupación mayor para el proveedor del servicio, ya que éste se relaciona con varias instituciones.  
  
## <a name="see-also"></a>Vea también  
 [Casos prácticos de seguridad para pequeñas y medianas empresas](../core/security-case-studies-for-small-to-medium-sized-companies.md)    
 [Escenarios de ejemplo para el análisis de modelo de amenaza](../core/sample-scenarios-for-threat-model-analysis.md)