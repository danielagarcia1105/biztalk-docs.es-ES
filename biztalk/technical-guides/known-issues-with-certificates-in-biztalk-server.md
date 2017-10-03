---
title: Problemas conocidos con certificados de servidor BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab58264b-2475-4831-9f08-bfbaa293022f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5aecfca9f58758e72f357439901684a0a617f3c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-certificates-in-biztalk-server"></a>Problemas conocidos relacionados con certificados de servidor BizTalk Server
Esta sección describen problemas conocidos relacionados con la administración de certificados digitales que se utiliza con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="general-certificate-issues"></a>Problemas generales de certificado  
  
### <a name="lack-of-connectivity-to-the-certificate-revocation-list-will-cause-a-certificate-to-be-rejected"></a>La falta de conectividad a la lista de revocación de certificados hará que un certificado que se rechacen  
 Este problema implica el siguiente error: "se produjo un error de autenticación. El estado de la entidad de certificación (CA) que emitió el certificado usado para firmar el mensaje es desconocido". Este error puede producirse cuando el certificado de firma es válido cuando se ve en MMC (mediante el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usuario) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Esta condición puede producirse si está habilitada la propiedad "Comprobar la revocación de certificados" en el componente de descodificador de S/MIME en la canalización de recepción. Cuando esta propiedad está establecida en true, el servidor BizTalk Server intentará consultar la lista de revocación de certificados (CRL) para ver si se ha revocado el certificado entrante. No importa si no se ha revocado el certificado en Sí. Si BizTalk Server no se puede consultar la lista CRL correspondiente debido a problemas de conectividad, no aceptará el certificado. Para solucionar este error, mostrar las propiedades del certificado haciendo doble clic en el certificado que usa. En la ficha Detalles, verá el atributo "Punto de distribución de CRL" en la lista de campos. Debería haber varias direcciones URL en este atributo que apuntan a la CRL en el servidor de entidad emisora de certificados. El servidor BizTalk server debe poder tener acceso a cualquiera de estas direcciones URL para recuperar la CRL. En caso contrario, se producirá un error en la comprobación de revocación y se mostrará el error anterior.  
  
### <a name="the-other-people-certificate-store-is-not-initialized-until-accessed"></a>No se ha inicializado el almacén de certificados otras personas hasta que tenga acceso  
 Este problema implica el siguiente error de almacén de certificados al intentar agregar o modificar envío/recepción puertos y ubicaciones mediante la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administrador de forma remota: "No se pudo abrir almacén de certificados". y "el sistema no encuentra el archivo especificado. (Sistema) ".  
  
> [!NOTE]  
>  Puede modificar estos artefactos mediante la consola de administración si se conecta directamente a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 En un equipo recién instalado, el **certificados otras personas** no está inicializado el almacén a menos que se puede acceder a ella una vez. Durante la configuración del grupo, puede inicializar esto **certificados otras personas** almacenar y como resultado no se muestre este error en un equipo en el grupo al que se ha realizado la configuración.  
  
### <a name="biztalk-server-only-supports-one-personal-certificate-for-each-biztalk-group"></a>BizTalk Server sólo admite un certificado personal para cada grupo de BizTalk  
 Los certificados personales que usan el grupo de BizTalk se especifica estableciendo la huella digital del certificado personal en las propiedades del grupo de BizTalk. Un grupo de BizTalk puede representar una empresa, un departamento, un concentrador u otra unidad de negocio.  
  
## <a name="as2-certificate-issues"></a>AS2 Problemas de certificados  
  
### <a name="the-as2-decoder-will-not-validate-that-a-certificate-is-configured-on-the-host-or-for-the-destination-party"></a>El descodificador AS2 no validará que un certificado está configurado en el host o para la entidad de destino  
 El descodificador AS2 descifrará un mensaje siempre que el certificado privado de dicho mensaje esté configurado en el almacén de certificados. Sin embargo, el descodificador AS2 no validará que el certificado de descifrado sea el mismo que el certificado configurado en el host. El mensaje recibido se puede cifrar con más de un certificado.  
  
### <a name="biztalk-server-will-be-unable-to-decrypt-a-message-saved-in-wire-format-if-the-certificate-is-not-valid"></a>BizTalk Server podrá descifrar un mensaje guardado con formato si el certificado no es válido  
 **Síntoma**  
  
 BizTalk Server no puede descifrar un mensaje AS2 entrante que se haya guardado con formato en la base de datos sin repudio.  
  
 **Causa posible**  
  
 El certificado necesario para descifrar el mensaje ha caducado o se ha revocado. Hay más probabilidades de que esto ocurra si ha transcurrido cierto período de tiempo desde que se guardó el mensaje AS2 en la base de datos sin repudio. Si esto ocurre, es posible que no disponga de acceso inmediato a un certificado válido para el mensaje.  
  
 **Resolución**  
  
 Adquiera un certificado válido para descifrar el mensaje.  
  
### <a name="if-an-as2-message-cannot-be-decrypted-the-problem-may-be-fixed-by-re-importing-the-certificate"></a>Si no se puede descifrar un mensaje AS2, se puede solucionar el problema al volver a importar el certificado  
 **Síntoma**  
  
 El descodificador AS2 encuentra una excepción cuando intenta descifrar un mensaje AS2, generando el error siguiente:  
  
```  
"The AS2 Decoder encountered an exception during processing. Details of the message and exception are as follows:   
   AS2-From:"PARTNER" AS2-To:"HOME" MessageID:"<137706.1178060412333@servername>"   
   MessageType: "unknown" Exception:"An error occurred when decrypting an AS2 message."  
System.ArgumentNullException: Value cannot be null.  
Parameter name: PayloadContentType  
at Microsoft.BizTalk.Edi.Reporting.Common.Utilities.ValidateArgument(Object o,  
String parameterName, Boolean isEmptyStringValidationRequired)  
at Microsoft.BizTalk.EdiInt.Reporting.AS2MessageActivity.ValidateParameters()  
at Microsoft.BizTalk.EdiInt.Reporting.AS2MessageActivity.Create()"  
  
```  
  
 **Causa posible**  
  
 Hay que volver a cargar el certificado usado para descifrar el mensaje AS2 en el almacén personal.  
  
 **Resolución**  
  
 Elimine el certificado existente del almacén personal y, a continuación, vuelva a importar el certificado en el almacén personal mediante el Asistente para importación de certificados. Para ello, con el botón secundario el **certificado** carpeta bajo la **almacén Personal**, seleccionando **todas las tareas**y, a continuación, haga clic en **importación**.  
  
### <a name="use-the-same-logon-for-the-in-process-host-instance-and-the-isolated-host-instance-to-ensure-that-personal-store-is-recognized"></a>Utilizar el mismo inicio de sesión de la instancia de host in-process y se reconoce la instancia de host aislado para asegurarse de que el almacén de personal  
 El almacén de certificados personales sólo estará disponible para el procesamiento de mensajes si el perfil del usuario está cargado para el usuario cuyas credenciales de inicio de sesión están asociadas a la instancia del host. El almacén personal se usa para los certificados de firma y descifrado (la clave privada propia del usuario). El perfil del usuario se carga de forma predeterminada para la instancia del host de tipo En curso; sin embargo, el perfil del usuario no se carga de forma predeterminada para la instancia del host aislado. Puede hacer que una aplicación cargue el perfil del usuario para el host aislado. Como alternativa, puede solucionar este problema usando el mismo inicio de sesión para la instancia del host de tipo En curso y la instancia del host aislado.  
  
 En lugar de que una aplicación cargue el perfil de usuario, puede crear un servicio vacío para cargar el perfil. Para obtener más información acerca de cómo crear un servicio vacío, vea [Cómo: crear servicios de Windows](http://go.microsoft.com/fwlink/?LinkId=155149) (http://go.microsoft.com/fwlink/?LinkId=155149) en la Ayuda de Visual Studio.  
  
 Después de crear el servicio vacío para cargar el perfil, haga lo siguiente:  
  
1.  Haga clic en **iniciar**y, a continuación, haga clic en **ejecutar** para abrir el **ejecutar** cuadro de diálogo.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **service.msc** y presione **ENTRAR** para abrir el **servicios** complemento MMC.  
  
3.  Abra la **propiedades** cuadro de diálogo para el servicio que creó. Haga clic en el servicio y seleccione **propiedades**.  
  
4.  Haga clic en el **iniciar sesión** ficha, seleccione **esta cuenta**y, a continuación, escriba el nombre de inicio de sesión utilizado para la instancia de host aislado.  
  
5.  Haga clic en **Aceptar**.  
  
6.  Inicie manualmente el servicio para cargar el perfil de usuario para dicho usuario de inicio de sesión.  
  
### <a name="the-key-usage-attribute-of-a-certificate-must-match-the-certificates-use"></a>El atributo Uso de la clave de un certificado debe coincidir con el uso del certificado.  
 Los certificados usados para el transporte AS2 deben tener los atributos necesarios para su uso previsto. Para la firma y la verificación de la firma, el atributo Uso de la clave del certificado debe ser Firma digital. Para el cifrado y el descifrado, el atributo Uso de la clave del certificado debe ser Cifrado de datos o Cifrado de clave. Puede comprobar el atributo de uso de clave haciendo doble clic en el certificado, haga clic en el **detalles** pestaña en el **certificado** cuadro de diálogo y comprobación de la **EKU** campo .  
  
### <a name="the-certificate-resolution-list-will-be-verified-for-an-outgoing-mdn-if-the-as2-to-property-is-not-set-for-the-party"></a>La lista de resolución de certificados se comprobará para un MDN saliente si la propiedad AS2-To no está configurada para la entidad.  
 En el acuerdo predeterminado para un MDN saliente, se realiza la verificación de la lista de resolución de certificados. Si no desea que se realice esta verificación, compruebe que está establecida la propiedad AS2-To correcta, de forma que la entidad de recepción pueda resolverse y las propiedades de la entidad puedan determinarse. En ese caso, no se usará el acuerdo predeterminado que solicita la verificación de la lista de resolución de certificados. También deberá deshabilitar la propiedad Comprobar lista de revocaciones de certificados de la página General de las propiedades de entidad AS2.