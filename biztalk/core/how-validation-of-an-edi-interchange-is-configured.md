---
title: Cómo configurar la validación de un intercambio EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e698b21-e234-4d7d-b101-742eff68155c
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06485274a0053846c361d1aaab6707a073c16958
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-validation-of-an-edi-interchange-is-configured"></a>Cómo configurar la validación de un intercambio EDI
Si el proceso de búsqueda de acuerdos determina el acuerdo en el que se resuelve un intercambio entrante o saliente, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará las propiedades del acuerdo (y no las propiedades de la canalización) para determinar el modo en que se realiza la validación. Si ningún acuerdo se resuelve en un intercambio, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará algunas propiedades del acuerdo de reserva y algunas propiedades de la canalización en la realización de la validación.  
  
 En las siguientes tablas se indica cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determina las validaciones que se van a realizar en un intercambio EDI. Para las columnas de acuerdo de reserva y canalización de la tabla, "Sí" significa que se usa dicha configuración si no se ha determinado ningún acuerdo.  
  
## <a name="general-information"></a>Información general  
  
|Validación|Configurada por el socio comercial|Configurada por la canalización<sup>*</sup>|Configurada por el acuerdo|Configurada por las opciones del acuerdo de reserva|  
|----------------|-----------------------------------|----------------------------------------|-----------------------------|-----------------------------------------------|  
|Asociaciones de puerto de envío|Sí|No|Sí|no|  
|Certificados|Sí|No|No|no|  
|Informes de estado|no|No|Sí|Sí|  
  
> [!NOTE]
>  Aunque la configuración está disponible a través de la canalización, Microsoft recomienda no configurar las propiedades en la canalización.  
  
## <a name="agreement-for-outbound-interchangesbiztalk-receive-pipeline"></a>Acuerdo para intercambios de salida o canalización de recepción de BizTalk  
  
|Validación|Configurada por el acuerdo|Configurada por la canalización<sup>*</sup>|Configurada por las opciones del acuerdo de reserva|  
|----------------|-----------------------------|----------------------------------------|-----------------------------------------------|  
|Información de perfil de negocio: detalles de contrato y póngase en contacto con|Sí|-|-|  
  
 **Validación de X12 propiedades de sobres**  
  
|Validación|Configurada por el acuerdo|Configurada por la canalización<sup>*</sup>|Configurada por las opciones del acuerdo de reserva|  
|----------------|-----------------------------|----------------------------------------|-----------------------------------------------|  
|Autorización/seguridad|Sí|Solo disponible en el nivel de acuerdo|Solo disponible en el nivel de acuerdo|  
|Id. de remitente|Sí|Solo disponible en el nivel de acuerdo|Solo disponible en el nivel de acuerdo|  
|RepSeparator/<br />ISA11|Sí|Sí|no|  
|Duplicar/validez en ISA|Sí|No|Sí|  
|Duplicar/validez en GS|Sí|No|Sí|  
|Duplicar/validez en ST|Sí|No|Sí|  
|NS/TS en nivel de grupo|Sí|No|Sí|  
|Versión y lanzamiento|Sí|Solo disponible en el nivel de acuerdo|Solo disponible en el nivel de acuerdo|  
  
 **Validación de propiedades sobre de EDIFACT**  
  
|Validación|Configurada por el acuerdo|Configurada por la canalización<sup>*</sup>|Configurada por las opciones del acuerdo de reserva|  
|----------------|-----------------------------|----------------------------------------|-----------------------------------------------|  
|Contraseña|Sí|Solo disponible en el nivel de acuerdo|Solo disponible en el nivel de acuerdo|  
|SenderID|Sí|Solo disponible en el nivel de acuerdo|Solo disponible en el nivel de acuerdo|  
|NS/TS en nivel de grupo|Sí|No|Sí|  
|Versión y lanzamiento|Sí|Solo disponible en el nivel de acuerdo|Solo disponible en el nivel de acuerdo|  
|Duplicar/validez en UNB|Sí|No|Sí|  
|Duplicar/validez en UNG|Sí|No|Sí|  
|Duplicar/validez en UNH|Sí|No|Sí|  
|Delimitadores UNA|no|Sí|no|  
  
 **Propiedades de confirmación generales**  
  
|Validación|Configurada por el acuerdo|Configurada por la canalización<sup>*</sup>|Configurada por las opciones del acuerdo de reserva|  
|----------------|-----------------------------|----------------------------------------|-----------------------------------------------|  
|Confirmación bidireccional|Sí|Sí|no|  
|Generar confirmación funcional|Sí|No|Sí|  
|Confirmación de intercambio de lotes|Sí|Solo disponible en el nivel de acuerdo|Solo disponible en el nivel de acuerdo|  
|Control de confirmación personalizado|Sí|No|Sí|  
|Generar confirmación de intercambio|Sí|No|Sí|  
|Confirmación de intercambio de lotes|Sí|Solo disponible en el nivel de acuerdo|Solo disponible en el nivel de acuerdo|  
|Control de confirmación personalizado|Sí|No|Sí|  
|Informes de control|Sí|No|Sí|  
  
 **Propiedades de validación en carga**  
  
|Validación|Configurada por el acuerdo|Configurada por la canalización<sup>*</sup>|Configurada por las opciones del acuerdo de reserva|  
|----------------|-----------------------------|----------------------------------------|-----------------------------------------------|  
|ENRUTAMIENTO|Sí|Sí|no|  
|Extendido|Sí|Sí|no|  
|Separadores finales|Sí|Sí|no|  
|Generar etiquetas para separadores finales|Sí|Sí|no|  
|Enmascaramiento de seguridad/contraseña|Sí|Sí|no|  
|Conversión decimal|Sí|Sí|no|  
|Procesar por lotes|-|-|-|  
|Conservar intercambio|Sí|Sí|no|  
  
> [!NOTE]
>  Aunque la configuración está disponible a través de la canalización, Microsoft recomienda no configurar las propiedades en la canalización.  
  
## <a name="agreement-for-inbound-interchangesbiztalk-send-pipeline"></a>Acuerdo para intercambios de entrada o canalización de envío de BizTalk  
 **X12 generación de sobres**  
  
|Validación|Configurada por el acuerdo|Configurada por la canalización<sup>*</sup>|Configurada por las opciones del acuerdo de reserva|  
|----------------|-----------------------------|----------------------------------------|-----------------------------------------------|  
|Segmentos ISA/GS/ST|Sí|No|Sí|  
  
 **Generación de sobres EDIFACT**  
  
|Validación|Configurada por el acuerdo|Configurada por la canalización<sup>*</sup>|Configurada por las opciones del acuerdo de reserva|  
|----------------|-----------------------------|----------------------------------------|-----------------------------------------------|  
|Segmentos UNA/UNB/UNG/UNH|Sí|No|Sí|  
|Delimitadores UNA|Sí|No|Sí|  
  
 **Configuración de confirmación esperada**  
  
|Validación|Configurada por el acuerdo|Configurada por la canalización<sup>*</sup>|Configurada por las opciones del acuerdo de reserva|  
|----------------|-----------------------------|----------------------------------------|-----------------------------------------------|  
|Configuración de confirmación Fn|Sí|Solo disponible en el nivel de acuerdo|Solo disponible en el nivel de acuerdo|  
  
 **Propiedades de validación en carga**  
  
|Validación|Configurada por el acuerdo|Configurada por la canalización<sup>*</sup>|Configurada por las opciones del acuerdo de reserva|  
|----------------|-----------------------------|----------------------------------------|-----------------------------------------------|  
|ENRUTAMIENTO|Sí|Sí|no|  
|Extendido|Sí|Sí|no|  
|Generación de separadores finales|Sí|Sí|no|  
  
 **Creación de lotes**  
  
|Validación|Configurada por el acuerdo|Configurada por la canalización<sup>*</sup>|Configurada por las opciones del acuerdo de reserva|  
|----------------|-----------------------------|----------------------------------------|-----------------------------------------------|  
|Criterios de versión|Sí|Solo disponible en el nivel de acuerdo|Solo disponible en el nivel de acuerdo|  
|Intervalo|Sí|Solo disponible en el nivel de acuerdo|Solo disponible en el nivel de acuerdo|  
|Filtros|Sí|Solo disponible en el nivel de acuerdo|Solo disponible en el nivel de acuerdo|  
  
> [!NOTE]
>  Aunque la configuración está disponible a través de la canalización, Microsoft recomienda no configurar las propiedades en la canalización.  
  
## <a name="see-also"></a>Vea también  
 [Validación de mensajes EDI](../core/edi-message-validation.md)