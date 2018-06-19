---
title: Problemas conocidos con la seguridad de AS2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b291e000-630d-49a1-8e19-f76c4dfee294
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bb633e092ed568bb3817df7be788364934be446
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262404"
---
# <a name="known-issues-with-as2-security"></a>Problemas conocidos de la seguridad de AS2
En este tema se describen los problemas conocidos en relación con la seguridad de soluciones AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="the-as2-decoder-will-not-validate-that-a-certificate-is-configured-on-the-host-or-for-the-destination-party"></a>El descodificador AS2 no validará que un certificado esté configurado en el host o para la entidad de destino.  
 El descodificador AS2 descifrará un mensaje siempre que el certificado privado de dicho mensaje esté configurado en el almacén de certificados. Sin embargo, el descodificador AS2 no validará que el certificado de descifrado sea el mismo que el certificado configurado en el host. El mensaje recibido se puede cifrar con más de un certificado.  
  
## <a name="storing-as2-messages-in-wire-format-can-lead-to-a-security-issue"></a>El almacenamiento de mensajes AS2 con formato puede derivar en un problema de seguridad.  
 Cuando no se usan certificados, no se recomienda el almacenamiento de mensajes AS2 con formato en la base de datos de recepción sin repudio (NRR). Si se hace, podría producirse un problema de seguridad.  
  
## <a name="messages-or-mdns-to-be-stored-in-the-nrr-database-should-be-signed"></a>Se deben firmar los mensajes o MDN que se vayan a almacenar en la base de datos NRR.  
 Para garantizar la recepción sin repudio, debe establecer la autenticación e integridad del mensaje correspondiente. La forma recomendada de hacerlo es mediante una firma digital en el mensaje. Como resultado, si configura las propiedades de la entidad AS2 para almacenar mensajes o MDN en la base de datos sin repudio, debe configurar las propiedades de AS2 para firmar los mensajes o MDN que vaya a almacenar.  
  
## <a name="biztalk-server-will-be-unable-to-decrypt-a-message-saved-in-wire-format-if-the-certificate-is-not-valid"></a>BizTalk Server no podrá descifrar un mensaje guardado con formato si el certificado no es válido.  
 **Síntoma**  
  
 BizTalk Server no puede descifrar un mensaje AS2 entrante que se haya guardado con formato en la base de datos sin repudio.  
  
 **Causa posible**  
  
 El certificado necesario para descifrar el mensaje ha caducado o se ha revocado. Hay más probabilidades de que esto ocurra si ha transcurrido cierto período de tiempo desde que se guardó el mensaje AS2 en la base de datos sin repudio. Si esto ocurre, es posible que no disponga de acceso inmediato a un certificado válido para el mensaje.  
  
 **Resolución**  
  
 Adquiera un certificado válido para descifrar el mensaje.  
  
## <a name="the-inner-envelope-of-a-signed-as2-message-must-not-be-changed-after-the-signature-has-been-calculated"></a>El sobre interno de un mensaje AS2 firmado no debe cambiarse después de que se haya calculado la firma.  
 Cuando se firma un mensaje AS2, la firma se calcula según los encabezados y la carga del sobre interno. Si se modifica el sobre interno tras el cálculo de la firma, ésta se deteriorará. Los encabezados de límite, o cualquier elemento fuera de los encabezados de límite, pueden modificarse, pero no se debe cambiar nada que se encuentre dentro de estos encabezados.  
  
## <a name="use-the-same-logon-for-the-in-process-host-instance-and-the-isolated-host-instance-to-ensure-that-personal-store-is-recognized"></a>Usar el mismo inicio de sesión para la instancia de host de tipo En curso y aislado para garantizar que se identifique el almacén personal.  
 El almacén de certificados personales sólo estará disponible para el procesamiento de mensajes si el perfil del usuario está cargado para el usuario cuyas credenciales de inicio de sesión están asociadas a la instancia del host. El almacén personal se usa para los certificados de firma y descifrado (la clave privada propia del usuario). El perfil del usuario se carga de forma predeterminada para la instancia del host de tipo En curso; sin embargo, el perfil del usuario no se carga de forma predeterminada para la instancia del host aislado. Puede hacer que una aplicación cargue el perfil del usuario para el host aislado. Como alternativa, puede solucionar este problema usando el mismo inicio de sesión para la instancia del host de tipo En curso y la instancia del host aislado.  
  
 En lugar de que una aplicación cargue el perfil de usuario, puede crear un servicio vacío para cargar el perfil. Para obtener información acerca de cómo crear un servicio vacío, vea [Cómo: crear servicios de Windows](http://go.microsoft.com/fwlink/?LinkId=196492). Después de haber creado el servicio, abra el cuadro de diálogo de administración de equipos, abra el cuadro de diálogo de propiedades para el servicio, haga clic en el **iniciar sesión** ficha, seleccione **esta cuenta**, escriba el nombre de inicio de sesión utilizado para el aislamiento de la instancia de host y, a continuación, haga clic en **Aceptar**. A continuación, puede iniciar manualmente el servicio para cargar el perfil de usuario de ese usuario de inicio de sesión.  
  
## <a name="the-key-usage-attribute-of-a-certificate-must-match-the-certificates-use"></a>El atributo Uso de la clave de un certificado debe coincidir con el uso del certificado.  
 Los certificados usados para el transporte AS2 deben tener los atributos necesarios para su uso previsto. Para la firma y la verificación de la firma, el atributo Uso de la clave del certificado debe ser Firma digital. Para el cifrado y el descifrado, el atributo Uso de la clave del certificado debe ser Cifrado de datos o Cifrado de clave. Para verificar el atributo Uso de la clave, haga doble clic en el certificado, haga clic en la ficha Detalles del cuadro de diálogo Certificado y compruebe el campo Uso de la clave.  
  
## <a name="the-certificate-resolution-list-will-be-verified-for-an-outgoing-mdn-if-the-as2-to-property-is-not-set-for-the-party"></a>La lista de resolución de certificados se comprobará para un MDN saliente si la propiedad AS2-To no está configurada para la entidad.  
 En el acuerdo predeterminado para un MDN saliente, se realiza la verificación de la lista de resolución de certificados. Si no desea que se realice esta verificación, compruebe que está establecida la propiedad AS2-To correcta, de forma que la entidad de recepción pueda resolverse y las propiedades de la entidad puedan determinarse. En ese caso, no se usará el acuerdo predeterminado que solicita la verificación de la lista de resolución de certificados. También deberá deshabilitar la propiedad Comprobar lista de revocaciones de certificados de la página General de las propiedades de entidad AS2.