---
title: Seguridad en tiempo de ejecución del servidor | Documentos de Microsoft
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
ms.openlocfilehash: 9a5979162a521185b87977191c9d709fb754b1ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214132"
---
# <a name="server-runtime-security"></a>Seguridad del servidor en tiempo de ejecución
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]Reparación de mensajes y nuevo envío rige el flujo de mensajes SWIFT entre los usuarios empresariales, sistemas back-end y los puntos de conexión de red SWIFT de forma segura y determinista. Mensajes enviados por los usuarios empresariales se autentica, valida los mensajes de datos y la exactitud de la regla de negocios y enruta los mensajes con sistemas back-end o para la entrega final a la red SWIFT. Para obtener más información acerca de los certificados digitales, vea "Cifrado y firma de certificados" en el sitio Web de MSDN Library en [http://go.microsoft.com/fwlink/?linkid=50285](http://go.microsoft.com/fwlink/?linkid=50285).  
  
 Reparación de mensajes y nuevo envío es un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación de orquestación, hospedan y ejecutan en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] contexto de seguridad. Se protege como un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] características de seguridad descritas anteriormente. Reparación de mensajes y nuevo envío también define y exige directivas de seguridad de nivel de usuario específicas para la creación del mensaje SWIFT, reparación, aprobación y envío, como se indica a continuación:  
  
-   Todos los mensajes, nuevos o reparados, se envían a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] a través de reparación de mensajes y nuevo envío deben originarse a partir de un usuario de confianza.  
  
-   Los usuarios de confianza que creen o reparación mensajes deben tener la autorización correcta y derechos. Los usuarios de confianza que aprobación o rechazan los mensajes deben tener la autorización correcta y derechos.  
  
-   Todos los mensajes deben ser aprobados por un número limitado de usuarios de confianza. Cada usuario de confianza en la cadena del creador del mensaje, Taller de reparación y aprobadores debe ser único, el mismo usuario no puede crear o reparar y aprobar o rechazar un mensaje. El mismo usuario no puede especificar varios aprobar o rechazar las decisiones para un único mensaje en un proceso de aprobación de varios pasos. No se puede aprobar sus propios mensajes creados o reparados, ni puede aprobar el mismo mensaje que varios aprobadores.  
  
-   No se puede modificar un mensaje durante el proceso de aprobación (es decir, un mensaje no se puede modificar después de envío original para la reparación de mensajes y nuevo envío, como un mensaje nuevo o reparado).  
  
-   Mensajes modificados durante una fase de comprobación de regeneración de claves deben coincidir exactamente con el mensaje original (creada o reparar).  
  
 Para aplicar esta semántica de seguridad, reparación de mensajes y nuevo envío valida la firma digital incrustada en todos los mensajes XML que recibe, en cada fase del proceso de envío de aprobación de creación o la reparación. La validación de firma digital de reparación de mensajes y nuevo envío realiza las siguientes comprobaciones. Si una o varias de estas comprobaciones producirá un error, reparación de mensajes y nuevo envío se detiene y se mantiene en el cuadro de mensaje y un error de seguridad se registran en el registro de eventos:  
  
-   El mensaje XML debe estar firmado digitalmente y, por tanto, debe contener una firma digital correspondiente.  
  
-   Cada firma digital usada en el flujo de trabajo debe hacerse mediante un certificado digital de confianza. Esto garantiza que el creador del mensaje, Taller de reparación, Comprobador y aprobadores son de confianza.  
  
-   Cada certificado digital de confianza debe pertenecer a un [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] usuario del dominio que tiene habilitada la pertenencia al grupo de dominio tienen autoridad lógico o derechos para realizar acciones en [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. Esto garantiza que cada participante en el proceso de crear o envío de aprobación de reparación tiene los derechos para realizar la acción específica que realiza o entidad correcta.  
  
     Las reglas anteriores se aplican a través de las ACL en el sitio de SharePoint a través de grupos de usuarios del sitio y el código de envío de formulario. Si el usuario que actúa sobre el mensaje no se encuentra en la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] grupo de usuarios (dominio o local), reparación de mensajes y nuevo envío rechaza el mensaje.  
  
     Por ejemplo, una organización que aplica un proceso de aprobación de tres fases podría definir estas tres funciones lógicas: talleres de reparación, comprobadores (fase de regeneración de claves) y aprobadores. En consecuencia, los usuarios participan en los roles deben pertenecer a la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] grupo de dominio de los usuarios. Para bloquear aún más el sitio de SharePoint, los usuarios deben organizarse en grupos de dominio lógico (por ejemplo, talleres de reparación, comprobadores, los aprobadores).  
  
     Para obtener más información acerca de grupos de usuarios del sitio, consulte [seguridad de Windows SharePoint Services](../../adapters-and-accelerators/accelerator-swift/windows-sharepoint-services-security.md).  
  
-   Cada firma digital en la pila debe ser único. Es decir, cada firma digital debe hacerse mediante un certificado digital único (en relación con las otras firmas en la misma pila). Esto garantiza que el mensaje no ha sido aprobado por la persona que creó o repara el mensaje y que ninguna persona aprueba el mismo mensaje que varios aprobadores.  
  
 Reparación de mensajes y nuevo envío impone las directivas de seguridad estricta haciendo que los puntos de comprobación en cada punto de entrada en la infraestructura de creación, reparación, aprobación y envío de mensajes. Estos puntos se complementan estrechamente con la funcionalidad básica de reparación de mensajes y nuevo envío y no pueden evitarse. Mientras la reparación de mensajes y nuevo envío está diseñado para integrarse a la perfección con los [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] funcionalidad de firma de formularios, también se ha diseñado para ser seguro y lo suficientemente fiable como para exigir la autenticidad y la protección de aunque se utilicen los mensajes de SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] es no usa y los mensajes se envían directamente por los usuarios finales a reparación de mensajes y nuevo envío recepción extremos (las carpetas SharePoint Web).