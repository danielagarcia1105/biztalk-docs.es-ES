---
title: Características de seguridad de BizTalk Server | Microsoft Docs
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
ms.openlocfilehash: 45d541138d566eb6791385cdb23413187d2e68ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971133"
---
# <a name="biztalk-server-security-features"></a>Características de seguridad de BizTalk Server
Desarrollan con aplicaciones de servicios financieras y las soluciones de integración [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] son [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicaciones y están protegidos por nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] características de seguridad. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] las aplicaciones normalmente se componen de funcionalidad de mensajería (mensaje de procesamiento, transformación, enrutamiento) y la automatización del flujo de trabajo (automatización de procesos empresariales, las reglas de negocios y evaluación lógica). [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona seguridad de automatización general de mensajería y flujo de trabajo. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] proporciona características de seguridad adicionales específicas para proteger el envío, reparación, aprobación y entrada de mensaje para el usuario final. Para obtener más información acerca de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]-seguridad específicos, consulte [A4SWIFT características de seguridad de reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/a4swift-security-features-for-message-repair-and-new-submission.md).  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se ha diseñado en torno a un modelo de evento mensajería (centrado en el patrón de diseño de base de datos y el publicador y suscriptor del cuadro de mensajes) en el que los mensajes y documentos, así como los componentes de procesamiento que interactúen con ellos, se basan en XML y servicios Web tecnologías. Para ayudar a proteger la integridad de cualquier sistema que se compone de información, los participantes y procesos, los siguientes requisitos principales guían mecanismos de seguridad:  
  
- **Proteger la privacidad de los elementos del sistema.** Proteger la privacidad de las comunicaciones de una informática abierto y entorno de red son la función de cifrado. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] es compatible con cifrado de las comunicaciones a través de la infraestructura de clave pública (PKI), Secure Multipurpose Internet Mail Extensions (S/MIME) y capa de Sockets seguros (SSL). Para autenticar y mejorar la protección de la privacidad de mensajes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] hace un gran uso de certificados digitales (claves).  
  
   PKI es el conjunto de protocolos de Internet que abordan las metodologías que promueven el intercambio seguro de claves, los procedimientos y la jerarquía de autoridad para la autenticación de claves y los algoritmos que implementa para estos fines.  
  
   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] usa el protocolo de S/MIME para cifrar y descifrar los mensajes enviados y recibidos en los procesos de varios pasos, de varias partes con el estándar de cifrado de datos (DES), 3DES y compatibilidad con algoritmos de cifrado RC2. Para la comunicación de cifrado punto a punto entre un cliente Web y un servidor Web, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] utiliza el protocolo SSL.  
  
- **Autenticación de información, los participantes y procesos.** Para autenticar la información, los participantes y procesos, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se basa en la firma de certificados, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación y una implementación extendida de [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] conocido como único empresarial Inicie la sesión (SSO). Certificados de firma son los certificados digitales (o claves) que identifican dos entidades entre sí en un intercambio de mensajería. Un certificado de firma también determina si un mensaje ha sido alterado durante el tránsito.  
  
   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Puede utilizar las claves públicas almacenadas para descodificar los mensajes entrantes firmados digitalmente y puede usar las claves privadas para firmar mensajes de salida que genera. SSO es la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] extensión [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación que permite a las partes y los eventos de mensajería que actúan en varios pasos [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] procesos para autenticarse en cualquier paso en el proceso, a cualquier recurso en el proceso, sin requerir varios inicios de sesión.  
  
- **Autorizar el uso de recursos.** La autorización es la asignación y administración de derechos de uso a los recursos de un sistema. La principal [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] son mecanismos de autorización [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Roles, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación y la base de datos de cuadro de mensajes. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] almacena todos los mensajes entrantes y salientes en su base de datos de cuadro de mensajes antes de enviarlos a un proceso de orquestación y, después de que la orquestación envía los mensajes a una canalización de envío. Acceso a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] bases de datos y los recursos se asigna a administradores, usuarios y cuentas de host mediante [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Roles.  
  
  El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] arquitectura de seguridad se basa en un sólido conjunto de mecanismos que se implementan a lo largo de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] mediante una variedad de metodologías diseñado para aumentar la seguridad. El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] componentes que incorporan los mecanismos de seguridad son envío y recepción de adaptadores, canalizaciones, la base de datos de cuadro de mensajes, las orquestaciones y las propiedades de contexto de seguridad del mensaje.  
  
  Estos componentes usar canalizaciones requerida autenticación, varios hosts lógicos y su propiedad "Autenticación de confianza" y las metodologías de publicar y suscribirse y recibir autorización para implementar los mecanismos de seguridad. Esta arquitectura de seguridad multifacética de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona numerosas opciones para ayudar a diseñar y ejecutar más seguros mensajería de servicios financieros y flujo de trabajo aplicaciones de automatización.