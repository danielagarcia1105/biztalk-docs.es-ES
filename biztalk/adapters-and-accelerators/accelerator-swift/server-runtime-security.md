---
title: Seguridad del servidor en tiempo de ejecución | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, server runtime
- servers, security
- servers, runtime
ms.assetid: 40f5ca3e-d9d3-4543-bd38-82283c343b76
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c690c6e34e5ac8d5f70bc58cfd36e4e99006e8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976269"
---
# <a name="server-runtime-security"></a>Seguridad del servidor en tiempo de ejecución
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Reparación de mensajes y nuevo envío rige el flujo de mensajes SWIFT entre los usuarios empresariales, los sistemas back-end y los puntos de conexión de red SWIFT en forma segura y determinista. Autentica los mensajes enviados por los usuarios empresariales, valida los mensajes para los datos y la exactitud de la regla de negocios y enruta los mensajes a sistemas de back-end o para la entrega final a la red SWIFT. Para obtener más información acerca de los certificados digitales, vea "Certificados de cifrado y firma" en el sitio Web de MSDN Library en [ http://go.microsoft.com/fwlink/?linkid=50285 ](http://go.microsoft.com/fwlink/?linkid=50285).  
  
 Reparación de mensajes y nuevo envío es un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] la aplicación de orquestación, hospeda y ejecuta en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] contexto de seguridad. Se protege como un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] características de seguridad se ha descrito anteriormente. Reparación de mensajes y nuevo envío también define y refuerza directivas de seguridad de nivel de usuario específicas para la creación de mensajes SWIFT, reparación, aprobación y envío, como se indica a continuación:  
  
- Todos los mensajes, nuevo o reparados, se envían a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] deben originarse a través de reparación de mensajes y nuevo envío de un usuario de confianza.  
  
- Los usuarios de confianza que crean o reparación de mensajes deben tener derechos y autorización correcta. Los usuarios de confianza que aprobar o rechazar los mensajes deben tener derechos y autorización correcta.  
  
- Todos los mensajes deben ser aprobados por un número limitado de usuarios de confianza. Cada usuario de confianza de la cadena de mensaje creador, Taller de reparación y los aprobadores debe ser único, el mismo usuario no puede crear o reparar y aprobar o rechazar un mensaje. El mismo usuario no puede especificar varios aprobar o rechazar las decisiones para un único mensaje en un proceso de aprobación de varios pasos. No se puede aprobar sus propios mensajes creados o reparados, ni puede aprobar el mismo mensaje que varios aprobadores.  
  
- No se puede modificar un mensaje durante el proceso de aprobación (es decir, un mensaje no se puede modificar después de envío original para la reparación de mensajes y nuevo envío, como un mensaje nuevo o reparado).  
  
- Los mensajes que se modifica durante una fase de comprobación de regeneración de claves deben coincidir exactamente con el mensaje original (creada o reparar).  
  
  Para aplicar esta semántica de seguridad, reparación de mensajes y nuevo envío valida la firma digital incrustada en todos los mensajes XML que recibe, en cada fase del proceso de aprobación: envío de creación o la reparación. La validación de firma digital de reparación de mensajes y nuevo envío realiza las siguientes comprobaciones. Si una o varias de estas comprobaciones producirá un error, reparación de mensajes y nuevo envío se detiene y se mantiene en el cuadro de mensaje y un error de seguridad se registran en el registro de eventos:  
  
- El mensaje XML debe estar firmado digitalmente y, por tanto, debe contener una firma digital correspondiente.  
  
- Cada firma digital usada del flujo de trabajo debe hacerse mediante un certificado digital de confianza. Esto garantiza que el creador del mensaje, Taller de reparación, Comprobador y aprobadores son de confianza.  
  
- Cada certificado digital de confianza debe pertenecer a un [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] usuario de dominio que tiene pertenencia en el grupo de dominio que tienen autoridad lógico o derechos para realizar acciones en [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. Esto garantiza que cada participante en el proceso de creación o el envío de aprobación de reparación tiene los derechos para realizar la acción específica que realiza o entidad correcta.  
  
   Las reglas anteriores se aplican a través de las ACL en el sitio de SharePoint a través de grupos de usuarios del sitio y el código de envío de formulario. Si el usuario que actúa sobre el mensaje no está en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] grupo de usuarios (dominio o local), reparación de mensajes y nuevo envío rechaza el mensaje.  
  
   Por ejemplo, una organización que aplica un proceso de aprobación de tres fases puede definir estas tres funciones lógicas: reparadores, comprobadores (escenario de regeneración de claves) y los aprobadores. En consecuencia, los usuarios que participan en los roles deben pertenecer a la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] grupo de dominio de los usuarios. Para bloquear aún más el sitio de SharePoint, los usuarios deben organizarse en grupos de dominio lógico (por ejemplo, talleres, comprobadores y aprobadores).  
  
   Para obtener más información acerca de grupos de usuarios del sitio, consulte [seguridad de Windows SharePoint Services](../../adapters-and-accelerators/accelerator-swift/windows-sharepoint-services-security.md).  
  
- Cada firma digital en la pila debe ser único. Es decir, debe realizarse cada firma digital mediante un certificado digital único (con respecto a otras firmas en la misma pila). Esto garantiza que el mensaje no ha sido aprobado por la persona que creó o repara el mensaje y que ninguna persona aprueba el mismo mensaje que varios aprobadores.  
  
  Reparación de mensajes y nuevo envío impone las directivas de seguridad estricta haciendo que los puntos de comprobación en cada punto de entrada en la infraestructura de creación, reparación, aprobación y envío de mensajes. Estos puntos de control están vinculados estrechamente con la funcionalidad básica de reparación de mensajes y nuevo envío y no pueden evitarse. Aunque la reparación de mensajes y nuevo envío está diseñado para integrarse sin problemas con la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] funcionalidad de firma de formularios, también está diseñado para ser seguro y lo suficientemente robusta para aplicar protección of si los mensajes de SWIFT y autenticidad [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] es no se usa y los mensajes se envían directamente por los usuarios finales a reparación de mensajes y nuevo envío recibir los puntos de conexión (carpetas de Web de SharePoint).