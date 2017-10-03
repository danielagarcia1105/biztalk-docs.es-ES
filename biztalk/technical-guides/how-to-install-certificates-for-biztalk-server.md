---
title: "Cómo instalar certificados de servidor BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70a89595-8828-4872-b78b-77e9b0b048b8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d799956d25bfe8e494fcbc2fbc6cbea770a92fdb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-certificates-for-biztalk-server"></a>Cómo instalar certificados de servidor BizTalk Server
Para ayudar a proteger de transferencia de datos en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe agregar el certificado apropiado en el almacén de certificados adecuado y asociar los certificados a los artefactos de BizTalk adecuados. Este tema describe cómo mostrar la interfaz de la consola de administración de certificados para los almacenes de certificados del equipo Local y el usuario actual y cómo instalar el certificado adecuado en el almacén adecuado.  
  
 Los certificados que se muestra en la siguiente tabla se usan para ayudar a inicio de sesión, comprobar la firma para, cifrar y descifrar los mensajes.  
  
|Uso de certificados|Tipo de certificado|Almacén de certificados|  
|-----------------------|----------------------|-----------------------|  
|Firma (salida)|Clave privada propia (.pfx)|Usuario actual\\<br />Almacén personal de cada servidor de BizTalk que aloja una canalización de codificador MIME/SMIME como cada cuenta de servicio de la instancia de host|  
|Comprobación de firma (entrada)|Clave pública de socio comercial (.cer)|Almacén de equipo local u otras personas de cada servidor de BizTalk Server que contiene una canalización del descodificador de MIME/SMIME como cuenta del servicio de instancias de host.|  
|Cifrado (salida)|Clave pública de socio comercial (.cer)|Almacén de equipo local u otras personas de cada servidor de BizTalk Server que contiene una canalización del codificador de MIME/SMIME.|  
|Descifrado (entrada)|Clave privada propia (.pfx)|Almacén del usuario actual o personal de cada servidor de BizTalk Server que contiene una canalización del descodificador de MIME/SMIME como cuenta del servicio de instancias de host.|  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos de este tema debe haber iniciado sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  
  
### <a name="to-display-the-certificates-management-console"></a>Para mostrar la consola de administración de certificados  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **MMC**y haga clic en **Aceptar** para abrir el **Microsoft Management Console**.  
  
2.  Haga clic en el **archivo** menú y, a continuación, haga clic en **agregar o quitar complemento** para mostrar la **agregar o quitar complemento** cuadro de diálogo.  
  
3.  Haga clic en el **agregar** botón para mostrar el **Add Standalone Snap-in** cuadro de diálogo.  
  
4.  Seleccione **certificados** en la lista de complementos y, a continuación, haga clic en **agregar**.  
  
5.  Seleccione **cuenta de equipo**, haga clic en **siguiente**y, a continuación, haga clic en **finalizar**. Esto agregará la **consola de administración de certificados** interfaz para **equipo Local**.  
  
6.  Asegúrese de que **certificados** sigue seleccionado en la lista de complementos y, a continuación, haga clic en **agregar** nuevo.  
  
7.  Seleccione **mi cuenta de usuario**y, a continuación, haga clic en **finalizar**. Esto agregará la **consola de administración de certificados** interfaz para **usuario actual**.  
  
    > [!NOTE]  
    >  Esto muestra la **consola de administración de certificados** para la cuenta que han iniciado sesión como. Si es necesario importar certificados en el almacén Personal para una cuenta de servicio, primero debe iniciar sesión con las credenciales de la cuenta de servicio.  
  
8.  Haga clic en el **cerrar** situado en la **Standalone Snap-in** cuadro de diálogo.  
  
9. Haga clic en el **Aceptar** situado en la **agregar o quitar complemento** cuadro de diálogo.  
  
### <a name="to-install-a-certificate-for-receiving-encrypted-messages"></a>Para instalar un certificado para recibir mensajes cifrados  
  
1.  Solicitar un par de claves pública y privada para firmas digitales de la entidad de certificación (CA) para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a usar.  
  
2.  Enviar al asociado de la clave pública para el cifrado.  
  
3.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión como la cuenta de servicio para la instancia de host que se está ejecutando el controlador que recibirá mensajes del socio comercial. Instalar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] certificado de clave privada para descifrar mensajes en el almacén personal de la cuenta de servicio.  
  
    > [!NOTE]  
    >  Para obtener más información sobre el procedimiento utilizado para instalar certificados para el cifrado, vea [cómo instalar los certificados para mensajes cifrados con](http://go.microsoft.com/fwlink/?LinkId=155156) (http://go.microsoft.com/fwlink/?LinkId=155156) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda. Para obtener más información acerca de la herramienta que se utiliza para importar un certificado en el almacén de certificados, consulte [certificado Asistente utilidad](http://go.microsoft.com/fwlink/?LinkId=155157) (http://go.microsoft.com/fwlink/?LinkId=155157) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
4.  Hacer que el socio comercial se instale el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] certificado de clave pública para cifrar los mensajes en el almacén adecuado. Si el socio comercial usa Windows 2000 Server, Windows Server 2003 o Windows Server 2008, estas personas deberían instalar la clave pública en el almacén otras personas.  
  
### <a name="to-install-a-certificate-for-sending-encrypted-messages"></a>Para instalar un certificado para enviar mensajes cifrados  
  
1.  Tener el asociado de solicitar un par de claves pública y privada para el cifrado de la entidad de certificación (CA).  
  
2.  Tiene el socio envía su clave pública para cifrar los mensajes que se envía al socio comercial.  
  
3.  Tener el asociado de instalar el certificado de clave privado para descifrar mensajes en el almacén adecuado. Si el socio comercial usa Windows 2000 Server, Windows Server 2003 o Windows Server 2008, estas personas deberían instalar la clave privada en el almacén de certificados personales.  
  
    > [!NOTE]  
    >  Para obtener más información sobre el procedimiento utilizado para instalar certificados para el cifrado, vea [cómo instalar los certificados para mensajes cifrados con](http://go.microsoft.com/fwlink/?LinkId=155156) (http://go.microsoft.com/fwlink/?LinkId=155156) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda. Para obtener más información acerca de la herramienta que se utiliza para importar un certificado en el almacén de certificados, consulte [certificado Asistente utilidad](http://go.microsoft.com/fwlink/?LinkId=155157) (http://go.microsoft.com/fwlink/?LinkId=155157) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
4.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión en el servidor que tiene una instancia de host que ejecuta un controlador que enviará mensajes al socio comercial. Instalar certificado de clave pública del socio para cifrar los mensajes enviados al socio en el almacén otras personas.  
  
### <a name="to-install-a-certificate-for-receiving-signed-messages"></a>Para instalar un certificado para recibir mensajes firmados  
  
1.  Tener el asociado de solicitar un par de claves pública y privada para firmas digitales de la entidad de certificación (CA).  
  
2.  Tiene el socio envía su clave pública para firmas digitales.  
  
3.  Hacer que el socio instale su certificado de clave privada para firmar los mensajes en el almacén adecuado. Si está utilizando Windows 2000 Server, Windows Server 2003 o Windows Server 2008, hacer que se instale la clave privada en el almacén personal de la cuenta que firmará los mensajes enviados a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
    > [!NOTE]  
    >  Para obtener más información sobre el procedimiento utilizado para instalar certificados para el cifrado, vea [cómo instalar los certificados para mensajes cifrados con](http://go.microsoft.com/fwlink/?LinkId=155156) ([http://go.microsoft.com/fwlink/?LinkId=155156](http://go.microsoft.com/fwlink/?LinkId=155156)) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda. Para obtener más información acerca de la herramienta que se utiliza para importar un certificado en el almacén de certificados, consulte [certificado Asistente utilidad](http://go.microsoft.com/fwlink/?LinkId=155157) (http://go.microsoft.com/fwlink/?LinkId=155156) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
4.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión en el servidor que tiene una instancia de host que ejecuta un controlador que recibirá mensajes del socio comercial. Instalar certificado de clave pública del socio para comprobar la firma en el almacén otras personas.  
  
### <a name="to-install-a-certificate-for-sending-signed-messages"></a>Para instalar un certificado para enviar mensajes firmados  
  
1.  Solicitar un par de claves pública y privada para firmas digitales de la entidad de certificación (CA) para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a usar.  
  
2.  Enviar al asociado de la clave pública para firmas digitales.  
  
3.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión como la cuenta de servicio para la instancia de host que se está ejecutando el controlador que enviará mensajes al socio comercial. Instalar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] certificado de clave privada para firmar los mensajes en el almacén personal de la cuenta de servicio.  
  
    > [!NOTE]  
    >  Para obtener más información sobre el procedimiento utilizado para instalar certificados para el cifrado, vea [cómo instalar los certificados para mensajes cifrados con](http://go.microsoft.com/fwlink/?LinkId=155156) (http://go.microsoft.com/fwlink/?LinkId=155156) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda. Para obtener más información acerca de la herramienta que se utiliza para importar un certificado en el almacén de certificados, consulte [certificado Asistente utilidad](http://go.microsoft.com/fwlink/?LinkId=155157) (http://go.microsoft.com/fwlink/?LinkId=155157) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
4.  Hacer que el socio comercial se instale el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] certificado de clave pública para comprobar la firma digital en el almacén adecuado. Si el socio comercial usa Windows 2000 Server, Windows Server 2003 o Windows Server 2008, estas personas deberían instalar la clave pública en el almacén otras personas.