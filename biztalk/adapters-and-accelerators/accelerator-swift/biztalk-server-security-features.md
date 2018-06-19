---
title: Características de seguridad de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authentication
- security, authentication
- security, BizTalk Server
- security, security features
- BizTalk Server, security features
ms.assetid: db356439-1898-4c09-86de-458a9bd21b18
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58f87bab3118f824843167a7be97d831cecc0b7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211052"
---
# <a name="biztalk-server-security-features"></a>Características de seguridad de BizTalk Server
Las aplicaciones de servicios financieras y soluciones de integración desarrollan mediante [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] son [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicaciones y están protegen por nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] características de seguridad. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]las aplicaciones normalmente se componen de funcionalidad de mensajería (mensaje de procesamiento, transformación, enrutamiento) y la automatización del flujo de trabajo (automatización de procesos empresariales, las reglas de negocios y evaluación lógica). [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]proporciona seguridad de automatización general de mensajería y flujo de trabajo. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]proporciona características de seguridad adicionales específicas para proteger el envío, reparación, aprobación y entrada de mensaje para el usuario final. Para obtener más información acerca de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]-seguridad específicos, consulte [A4SWIFT las características de seguridad de reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/a4swift-security-features-for-message-repair-and-new-submission.md).  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]se ha diseñado basándose en un modelo de evento mensajería (centrado en el modelo de diseño de base de datos y el publicador y el suscriptor del cuadro de mensajes) en el que los mensajes y documentos, así como los componentes de procesamiento que interactúen con ellos, se basan en XML y los servicios Web tecnologías. Para ayudar a proteger la integridad de cualquier sistema que se compone de información, los participantes y procesos, los requisitos primarios siguientes guían de mecanismos de seguridad:  
  
-   **Proteger la privacidad de los elementos del sistema.** Entorno de red y proteger la privacidad de las comunicaciones en un cálculo abierta son la función de cifrado. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]es compatible con cifrado de las comunicaciones a través de la infraestructura de clave pública (PKI), extensiones seguras multipropósito de correo Internet (S/MIME) y capa de Sockets seguros (SSL). Para autenticar y mejorar la protección de la privacidad de los mensajes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] hace un gran uso de certificados digitales (claves).  
  
     PKI es el conjunto de protocolos de Internet que abordan las metodologías que promueven su intercambio seguro de claves, la jerarquía de entidad para la autenticación de claves y los algoritmos que se implementan para estos fines y procedimientos.  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]usa el protocolo de S/MIME para cifrar y descifrar los mensajes enviados y recibidos en procesos de varios pasos, varias partes, con el estándar de cifrado de datos (DES), 3DES y compatibilidad con algoritmos de cifrado RC2. Para la comunicación de cifrado punto a punto entre un cliente Web y un servidor Web, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] utiliza el protocolo SSL.  
  
-   **Autenticación de información, los participantes y procesos.** Para autenticar la información, los participantes y procesos, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se basa en certificados, de firma [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación y una implementación extendida de [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] conocido como único empresarial Sign-On (SSO). Certificados de firma son los certificados digitales (o claves) que identifican dos entidades entre sí en un intercambio de mensajería. Un certificado de firma también determina si un mensaje se ha alterado en tránsito.  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Puede usar las claves públicas almacenadas para descodificar firmados digitalmente los mensajes entrantes y puede usar las claves privadas para firmar mensajes de salida que genera. SSO es la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] extensión [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación que permite a las partes y los eventos de mensajería que actúan en varios pasos [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] procesos para autenticarse en cualquier paso en el proceso, a cualquier recurso en el proceso, sin requerir varios inicios de sesión.  
  
-   **Autorizar el uso de recursos.** La autorización es la asignación y administración de derechos de uso a los recursos del sistema. La principal [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] son mecanismos de autorización [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Roles, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación y la base de datos de cuadro de mensajes. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]almacena todos los mensajes entrantes y salientes en la base de datos de cuadro de mensajes antes de enviarlos a un proceso de orquestación y después de que la orquestación envía los mensajes a una canalización de envío. El acceso a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] bases de datos y recursos está asignado a administradores, usuarios y cuentas con host [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Roles.  
  
 El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] arquitectura de seguridad se basa en un conjunto robusto de mecanismos que se implementan a lo largo de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] con una variedad de metodologías diseñado para aumentar la seguridad. El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] componentes que incorporan los mecanismos de seguridad son envío y recepción de adaptadores, canalizaciones, la base de datos de cuadro de mensajes, las orquestaciones y propiedades de contexto de seguridad del mensaje.  
  
 Estos componentes usar canalizaciones requerida autenticación, varios hosts lógicos y su propiedad "Autenticación de confianza" y las metodologías de publicar y suscribirse y recibir autorización para implementar los mecanismos de seguridad. Esta arquitectura de seguridad multifacética de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona numerosas opciones para ayudar a diseñar y ejecutar más seguros mensajería de servicios financieros y flujo de trabajo de aplicaciones de automatización.