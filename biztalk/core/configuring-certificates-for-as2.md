---
title: Configurar certificados para AS2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c160f294-7529-4e0a-876c-5827feaed067
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb2f9c22ddf41eec4133710de8a775bf8ff0b044
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234660"
---
# <a name="configuring-certificates-for-as2"></a>Configurar certificados para AS2
Para asegurar la transferencia de datos AS2 usando el cifrado y las firmas digitales, debe haber instalado los certificados adecuados, además de la configuración de AS2 adecuada en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En este tema se describen los certificados necesarios, el modo de configurarlos y los problemas comunes que pueden plantear.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="certificates-required-for-as2-transport"></a>Certificados necesarios para el transporte AS2  
 Para contribuir a la protección de la transferencia de datos AS2, debe agregar el certificado adecuado al almacén de certificados correspondiente y asociar los certificados a los artefactos apropiados de BizTalk. Los siguientes certificados se usan para contribuir a la protección de los mensajes AS2:  
  
|Uso de certificados|Tipo de certificado|Componente de canalización|Contexto de usuario|Almacén de certificados|Ubicación de definición|  
|-----------------------|----------------------|------------------------|------------------|-----------------------|-------------------|  
|Firma (salida)|Clave privada propia (.pfx)|Codificador AS2|Cuenta usada por la instancia de host asociada al controlador de envío.|Usuario actual y almacén personal de cada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que aloja una canalización de codificador AS2 como cada cuenta de servicio de instancia de host|-   **Certificado** página de la **propiedades del grupo de** cuadro de diálogo. Es el certificado de firmas predeterminado que se usa al enviar documentos firmados.<br />-Puede invalidar la configuración del certificado predeterminado y usar certificados diferentes para distintas entidades. Puede hacerlo seleccionando **invalidar certificado de firma de grupo** en el **certificado de firma** página de la ficha de acuerdo unidireccional el **propiedades del acuerdo de** cuadro de diálogo cuadro y especifique un certificado de firma. Si se establece esta propiedad, cualquier mensaje de AS2 se resuelve en el acuerdo se firmarán con el certificado proporcionado en el **certificado de firma** página y no por el certificado proporcionado como parte de las propiedades del grupo de BizTalk.|  
|Comprobación de firma (entrada)|Clave pública de socio comercial (.cer)|Descodificador de AS2|Cuenta usada por la instancia de host asociada al controlador de recepción.|Equipo local y almacén de otras personas de cada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que aloja una canalización de descodificador AS2 como cada cuenta de servicio de instancia de host|**Certificado** página de la **propiedades de la entidad** cuadro de diálogo **Nota:** el certificado utilizado para comprobar una firma para una entidad debe ser única entre los certificados usados para comprobar las firmas de los otros usuarios.|  
|Cifrado (salida)|Clave pública de socio comercial (.cer)|Codificador AS2|Cuenta usada por la instancia de host asociada al controlador de envío.|Equipo local y almacén de otras personas de cada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que aloja una canalización de codificador AS2|**Certificado** página de la **propiedades de puerto de envío** cuadro de diálogo|  
|Descifrado (entrada)|Clave privada propia (.pfx)|Descodificador de AS2|Cuenta usada por la instancia de host asociada al controlador de recepción.|Usuario actual y almacén personal de cada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que aloja una canalización de descodificador AS2 como cada cuenta de servicio de instancia de host|El descodificador AS2 determinará el certificado según la información del certificado presente en el mensaje.<br /><br /> Para el descodificador de MIME de BizTalk, el certificado debe estar en el **certificado** página del host usado para recibir el mensaje. Todo ello no resulta necesario para el descodificador AS2.|  
  
## <a name="certificate-signing-for-outgoing-messages"></a>Firma de certificados para mensajes salientes  
 Los mensajes AS2 salientes se firman con un certificado predeterminado definido como parte de las propiedades del Grupo de BizTalk. Sin embargo, puede haber escenarios en los que la entidad que recibe los mensajes desee que éstos estén firmados con un certificado privado que ellos proporcionan o esperan que se use un certificado diferente al firmar mensajes salientes para ellos. Este escenario de firma de mensajes salientes con otros certificados se habilita si selecciona el **invalidar certificado de firma de grupo** en el **certificado de firma** página de la ficha de acuerdo unidireccional de la **propiedades del acuerdo** diálogo cuadro y especifique un certificado de firma. Si se especifica un certificado como parte del acuerdo AS2 para una entidad, ese certificado se usa para firmar mensajes salientes. Si no se define ningún certificado para la entidad, se usa el certificado predeterminado especificado como parte de las propiedades del Grupo de BizTalk.  
  
## <a name="adding-certificates-to-the-certificate-stores"></a>Agregar certificados a los almacenes de certificados  
 Para obtener más información, vea la sección "Mostrar la consola de administración de certificados" de [instalar certificados para los adaptadores de WCF](../core/installing-certificates-for-the-wcf-adapters.md), así como el [certificado Asistente utilidad](../core/certificate-wizard-utility.md) tema.  
  
> [!IMPORTANT]
>  El almacén de certificados personales sólo estará disponible para el procesamiento de mensajes si el perfil del usuario está cargado para el usuario cuyas credenciales de inicio de sesión están asociadas a la instancia del host. El almacén personal se usa para los certificados de firma y descifrado (la clave privada propia del usuario). El perfil del usuario se carga de forma predeterminada para la instancia del host de tipo En curso; sin embargo, el perfil del usuario no se carga de forma predeterminada para la instancia del host aislado. Puede hacer que una aplicación cargue el perfil del usuario para el host aislado. Como alternativa, puede solucionar este problema usando el mismo inicio de sesión para la instancia del host de tipo En curso y la instancia del host aislado.  
  
## <a name="generating-certificates"></a>Generar certificados  
 Los certificados se pueden obtener de una Entidad de certificación (CA); sin embargo, los pasos para solicitar un certificado pueden variar entre las CA. Revise la información proporcionada en el sitio web de la Autoridad de certificación antes de enviar la solicitud de certificado.  
  
> [!IMPORTANT]
>  Los certificados usados para el transporte AS2 deben tener los atributos necesarios para su uso previsto. Para firmar y comprobar la firma, el **EKU** atributo del certificado debe ser **firma Digital**. Para el cifrado y descifrado, el **EKU** atributo del certificado debe ser **cifrado de datos** o **cifrado de clave**. Puede comprobar la **EKU** atributo haciendo doble clic en el certificado, haga clic en el **detalles** pestaña en el **certificado** cuadro de diálogo y comprobando la **EKU** campo.  
  
 Puede generar certificados en Windows Server 2008 usando Servicios de servidor de certificados; sin embargo, es posible que el socio solo acepte estos certificados para las pruebas ya que su firma es automática en lugar de estar firmados por una CA pública. Para obtener más información sobre el uso de servicios de Certificate Server para solicitar certificados, descargue **Windows Server 2008 Active Directory certificado servicios guía paso a paso** de [guías paso a paso de Windows Server 2008 ](http://go.microsoft.com/fwlink/?LinkId=187916) ([http://go.microsoft.com/fwlink/?LinkId=187916](http://go.microsoft.com/fwlink/?LinkId=187916)).  
  
### <a name="to-configure-a-certificate-for-signing-outgoing-as2-messages"></a>Procedimiento para configurar un certificado para firmar mensajes AS2 salientes  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **grupo de BizTalk** nodo y, a continuación, haga clic en **propiedades**.  
  
2.  En el árbol de consola de la **propiedades del grupo de** cuadro de diálogo, haga clic en **certificado**.  
  
3.  En el **certificado** panel, haga clic en **examinar**, busque el certificado que desea usar para la firma y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  En lugar de escribir el nombre común del certificado, se puede especificar sólo la huella digital. Puede obtener la huella digital haciendo doble clic en el certificado en el almacén de certificados en MMC o en el sistema de archivos, haga clic en el **detalles** ficha, haga clic en el **huella digital** campo y copiar la huella digital .  
  
4.  Haga clic en **Aceptar**.  
  
### <a name="to-configure-a-certificate-for-signing-outgoing-as2-messages-for-a-specific-party"></a>Procedimiento para configurar un certificado para la firma de mensajes AS2 salientes para una entidad específica  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo. Desde el **entidades y perfiles empresariales** panel, desde el **contratos** sección, haga clic en el acuerdo que se crea para intercambiar mensajes con una entidad específica y haga clic en  **Propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, haga clic en **certificados de firma de**.  
  
3.  Seleccione el **certificado de firma de grupo de invalidación** casilla de verificación para usar el certificado proporcionado en esta página para firmar mensajes AS2 salientes y MDN.  
  
4.  Haga clic en **examinar** para mostrar la **Seleccionar certificado** cuadro de diálogo, donde podrá seleccionar el certificado de firma que se aplicará a los mensajes transmitidos por esta entidad.  
  
5.  El **nombre común** cuadro de texto muestra una descripción del certificado seleccionado.  
  
6.  El **huella digital** cuadro de texto muestra la huella digital del certificado. La huella digital del certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal (un número entre 0 y 9) o una letra de la A F.  
  
7.  Haga clic en **quitar certificado** para quitar el certificado seleccionado.  
  
8.  Haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
### <a name="to-configure-a-certificate-for-verifying-the-digital-signature-of-an-incoming-as2-messages"></a>Para configurar un certificado para la verificación de la firma digital de mensajes AS2 entrantes  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, abra la **grupo de BizTalk** nodo y, a continuación, haga clic en el **partes** nodo.  
  
2.  En el **entidades y perfiles empresariales** panel, el menú contextual de la entidad que va a recibir mensajes firmados y, a continuación, haga clic en **propiedades**.  
  
3.  En el árbol de consola, haga clic en **certificado**.  
  
4.  En el **certificado** panel, haga clic en **examinar**, busque el certificado que desea usar para comprobar la firma digital y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  En lugar de escribir el nombre común del certificado, se puede especificar sólo la huella digital. Puede obtener la huella digital haciendo doble clic en el certificado en el almacén de certificados en MMC o en el sistema de archivos, haga clic en el **detalles** ficha, haga clic en el **huella digital** campo y copiar la huella digital .  
  
5.  Haga clic en **Aceptar**.  
  
### <a name="to-configure-a-certificate-for-encrypting-an-outgoing-as2-messages"></a>Para configurar un certificado para el cifrado de mensajes AS2 salientes  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, abra la **grupo de BizTalk** nodo, abra el **aplicaciones** nodo y abra el nodo de la **aplicación** que contiene el puerto de envío que va a enviar el mensaje cifrado en.  
  
2.  Abra la **puertos de envío** nodo, haga clic en el puerto de envío y, a continuación, haga clic en **propiedades**.  
  
3.  En el árbol de consola, haga clic en **certificado**.  
  
4.  En el **certificado** panel, haga clic en **examinar**, busque el certificado que desea usar para el cifrado y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  En lugar de escribir el nombre común del certificado, se puede especificar sólo la huella digital. Puede obtener la huella digital haciendo doble clic en el certificado en el almacén de certificados en MMC o en el sistema de archivos, haga clic en el **detalles** ficha, haga clic en el **huella digital** campo y copiar la huella digital .  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad de AS2](../core/as2-security.md)   
 [Configurar la firma, compresión y cifrado en el transporte de AS2](../core/configuring-signing-compression-and-encryption-in-as2-transport.md)   
 [AS2 Arquitectura de la solución](../core/as2-solution-architecture.md)   
 [Instalación de certificados para los adaptadores de WCF](../core/installing-certificates-for-the-wcf-adapters.md)