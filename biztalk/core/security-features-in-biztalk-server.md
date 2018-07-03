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
- BizTalk Server, security
- Master Secret server, security
- security, Master Secret server
- security, runtime
- security, data
- deploying, security
- security, configuring
- runtime, security
- security, security features
- security, messages
- security, access control
- security, about security
- access control
- security, deploying
- data, security
- messages, security
ms.assetid: 5ab15023-fa71-439e-b3aa-420fe28806fa
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d904bc842cb04bdf9c1457440c838c8a78e5c8f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992621"
---
# <a name="security-features-in-biztalk-server"></a>Características de seguridad en BizTalk Server
Microsoft® BizTalk® Server proporciona una puerta de enlace estándar para enviar y recibir documentos dentro de una intranet y a través de Internet. Los mensajes enviados y recibidos por BizTalk Server pueden ser de importancia crucial para la empresa, por lo que es importante contemplar medidas para proteger esos mensajes y la información que contienen tanto durante su tránsito como durante su proceso y almacenamiento por BizTalk Server. En esta sección se proporciona información sobre las características de seguridad de BizTalk Server y cómo se pueden usar para ayudar a proteger sus datos y el entorno.  
  
 BizTalk Server utiliza las siguientes medidas para proteger los mensajes entrantes y salientes, para proteger la información de configuración y de tiempo de ejecución, así como para integrarse de forma segura con otras aplicaciones y sistemas:  
  
 **Seguridad de mensajes**  
  
- Autenticación del remitente de un mensaje. BizTalk Server puede autenticar al remitente de un mensaje (mediante la información del certificado o la seguridad integrada de Windows) con el fin de validar la identidad del remitente del mensaje. Para obtener más información, consulte [autenticación de mensajes de entrada](../core/inbound-message-authentication.md).  
  
- Autorización del receptor de un mensaje. Una vez recibido el mensaje, BizTalk Server puede determinar qué procesos y usuarios tienen permisos para recibirlo. Para obtener más información, consulte [autorización del receptor de un mensaje](../core/authorizing-the-receiver-of-a-message.md).  
  
  **En tiempo de ejecución y la configuración de seguridad**  
  
- **Control de acceso y protección de datos.** BizTalk Server utiliza el control de acceso para garantizar que sus procesos tienen límites adecuados y que se controla el acceso a la información crítica de la empresa. En otras palabras, BizTalk Server garantiza que los usuarios y las cuentas tengan los derechos de usuario mínimos necesarios para desempeñar sus tareas. Para obtener más información, consulte [Control de acceso y seguridad de los datos](../core/access-control-and-data-security.md).  
  
  **Seguridad integrada**  
  
- Enterprise Single Sign-On. BizTalk Server usa el Inicio de sesión único (SSO) empresarial para asegurarse de cifrar la información de configuración confidencial necesaria para los adaptadores y las ubicaciones de envío y recepción, garantizando así el almacenamiento y transmisión seguros de esa información por BizTalk Server. Para obtener más información, consulte [SSO utilizando](../core/using-sso.md).  
  
## <a name="see-also"></a>Vea también  
 [Diseñar las arquitecturas del sistema de BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md)   
 [Planear la seguridad de mensaje](../core/planning-message-security.md)   
 [Control de acceso y seguridad de los datos](../core/access-control-and-data-security.md)   
