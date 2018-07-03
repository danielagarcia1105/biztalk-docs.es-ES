---
title: Cómo instalar certificados para BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70a89595-8828-4872-b78b-77e9b0b048b8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7133134ddd37562ec30112549bb1a4ac16149b03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969805"
---
# <a name="how-to-install-certificates-for-biztalk-server"></a>Cómo instalar certificados para BizTalk Server
Para ayudar a proteger de transferencia de datos en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe agregar el certificado adecuado al almacén de certificados correspondiente y asociar los certificados a los artefactos de BizTalk correspondientes. Este tema describe cómo mostrar la interfaz de la consola de administración de certificados para los almacenes de certificados equipo Local y el usuario actual y cómo instalar el certificado adecuado en el almacén adecuado.  

 Los certificados que se muestra en la tabla siguiente se utilizan para la Ayuda de inicio de sesión, comprobar la firma para, cifrar y descifrar los mensajes.  

|Uso de certificados|Tipo de certificado|Almacén de certificados|  
|-----------------------|----------------------|-----------------------|  
|Firma (salida)|Clave privada propia (.pfx)|Usuario actual\\<br />Almacén personal de cada servidor BizTalk server que hospeda una canalización de codificador MIME/SMIME como cada cuenta de servicio de la instancia de host|  
|Comprobación de firma (entrada)|Clave pública de socio comercial (.cer)|Almacén de equipo local u otras personas de cada servidor de BizTalk Server que contiene una canalización del descodificador de MIME/SMIME como cuenta del servicio de instancias de host.|  
|Cifrado (salida)|Clave pública de socio comercial (.cer)|Almacén de equipo local u otras personas de cada servidor de BizTalk Server que contiene una canalización del codificador de MIME/SMIME.|  
|Descifrado (entrada)|Clave privada propia (.pfx)|Almacén del usuario actual o personal de cada servidor de BizTalk Server que contiene una canalización del descodificador de MIME/SMIME como cuenta del servicio de instancias de host.|  

## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos de este tema debe haber iniciado sesión como un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  

### <a name="to-display-the-certificates-management-console"></a>Para mostrar la consola de administración de certificados  

1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **MMC**y haga clic en **Aceptar** para abrir el **Microsoft Management Console**.  

2.  Haga clic en el **archivo** menú y, a continuación, haga clic en **agregar o quitar complemento** para mostrar el **agregar o quitar complemento** cuadro de diálogo.  

3.  Haga clic en el **agregar** botón para mostrar el **Add Standalone Snap-in** cuadro de diálogo.  

4.  Seleccione **certificados** en la lista de complementos y, a continuación, haga clic en **agregar**.  

5.  Seleccione **cuenta de equipo**, haga clic en **siguiente**y, a continuación, haga clic en **finalizar**. Esto agregará la **consola de administración de certificados** interfaz para **ordenador**.  

6.  Asegúrese de que **certificados** sigue seleccionado en la lista de complementos y, a continuación, haga clic en **agregar** nuevo.  

7.  Seleccione **mi cuenta de usuario**y, a continuación, haga clic en **finalizar**. Esto agregará la **consola de administración de certificados** interfaz para **usuario actual**.  

    > [!NOTE]  
    >  Esto muestra la **consola de administración de certificados** para la cuenta que actualmente ha iniciado sesión como. Si es necesario importar certificados en el almacén Personal para una cuenta de servicio, primero debe iniciar sesión con las credenciales de la cuenta de servicio.  

8.  Haga clic en el **cerrar** situado en la **Standalone Snap-in** cuadro de diálogo.  

9. Haga clic en el **Aceptar** situado en la **agregar o quitar complemento** cuadro de diálogo.  

### <a name="to-install-a-certificate-for-receiving-encrypted-messages"></a>Para instalar un certificado para recibir mensajes cifrados  

1. Solicitar un par de claves pública y privada para firmas digitales de la entidad de certificación (CA) para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a usar.  

2. Enviar al asociado de la clave pública para el cifrado.  

3. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión como la cuenta de servicio para la instancia de host que ejecuta el controlador que recibirá mensajes del socio. Instalar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] certificado de clave privada para descifrar los mensajes en el almacén personal para la cuenta de servicio.  

   > [!NOTE]
   >  Para obtener más información sobre el procedimiento utilizado para instalar certificados para cifrado, consulte [cómo instalar los certificados para mensajes cifrados](http://go.microsoft.com/fwlink/?LinkId=155156) (<http://go.microsoft.com/fwlink/?LinkId=155156>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda. Para obtener más información acerca de la herramienta usada para importar un certificado en el almacén de certificados, consulte [utilidad de Asistente de certificado](http://go.microsoft.com/fwlink/?LinkId=155157) (<http://go.microsoft.com/fwlink/?LinkId=155157>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  

4. Hacer que el asociado se instale el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] certificado de clave pública para cifrar los mensajes en el almacén adecuado. Si el socio comercial usa Windows 2000 Server, Windows Server 2003 o Windows Server 2008, debe instalar la clave pública en el almacén otras personas.  

### <a name="to-install-a-certificate-for-sending-encrypted-messages"></a>Para instalar un certificado para enviar mensajes cifrados  

1. Tener el asociado de solicitar un par de claves pública y privada para el cifrado de la entidad de certificación (CA).  

2. Tener el asociado de enviar su clave pública para cifrar los mensajes se envíen al socio comercial.  

3. Tener el asociado de instalar el certificado de clave privado para descifrar los mensajes en el almacén adecuado. Si el socio comercial usa Windows 2000 Server, Windows Server 2003 o Windows Server 2008, debe instalar la clave privada en el almacén de certificados personales.  

   > [!NOTE]
   >  Para obtener más información sobre el procedimiento utilizado para instalar certificados para cifrado, consulte [cómo instalar los certificados para mensajes cifrados](http://go.microsoft.com/fwlink/?LinkId=155156) (<http://go.microsoft.com/fwlink/?LinkId=155156>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda. Para obtener más información acerca de la herramienta usada para importar un certificado en el almacén de certificados, consulte [utilidad de Asistente de certificado](http://go.microsoft.com/fwlink/?LinkId=155157) (<http://go.microsoft.com/fwlink/?LinkId=155157>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  

4. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión en el servidor que tiene una instancia de host que ejecuta un controlador que enviará mensajes al socio comercial. Instale el certificado de clave pública del socio para cifrar los mensajes enviados al socio comercial en el almacén otras personas.  

### <a name="to-install-a-certificate-for-receiving-signed-messages"></a>Para instalar un certificado para recibir mensajes firmados  

1. Tener asociado un par de claves pública y privada para firmas digitales de solicitud de la entidad de certificación (CA).  

2. Tener el asociado de enviar su clave pública para firmas digitales.  

3. Hacer que el socio instale su certificado de clave privada para firmar los mensajes en el almacén adecuado. Si usa Windows 2000 Server, Windows Server 2003 o Windows Server 2008, que los instalen la clave privada en el almacén personal de la cuenta que firmará los mensajes enviados a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

   > [!NOTE]
   >  Para obtener más información sobre el procedimiento utilizado para instalar certificados para cifrado, consulte [cómo instalar los certificados para mensajes cifrados](http://go.microsoft.com/fwlink/?LinkId=155156) ([http://go.microsoft.com/fwlink/?LinkId=155156](http://go.microsoft.com/fwlink/?LinkId=155156)) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda. Para obtener más información acerca de la herramienta usada para importar un certificado en el almacén de certificados, consulte [utilidad de Asistente de certificado](http://go.microsoft.com/fwlink/?LinkId=155157) (<http://go.microsoft.com/fwlink/?LinkId=155156>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  

4. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión en el servidor que tiene una instancia de host que ejecuta un controlador que recibirá mensajes del socio. Instale el certificado de clave pública del socio para comprobar la firma en el almacén otras personas.  

### <a name="to-install-a-certificate-for-sending-signed-messages"></a>Para instalar un certificado para enviar mensajes firmados  

1. Solicitar un par de claves pública y privada para firmas digitales de la entidad de certificación (CA) para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a usar.  

2. Enviar al asociado de la clave pública para firmas digitales.  

3. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión como la cuenta de servicio para la instancia de host que ejecuta el controlador que enviará mensajes al socio comercial. Instalar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] certificado de clave privada para firmar los mensajes en el almacén personal para la cuenta de servicio.  

   > [!NOTE]
   >  Para obtener más información sobre el procedimiento utilizado para instalar certificados para cifrado, consulte [cómo instalar los certificados para mensajes cifrados](http://go.microsoft.com/fwlink/?LinkId=155156) (<http://go.microsoft.com/fwlink/?LinkId=155156>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda. Para obtener más información acerca de la herramienta usada para importar un certificado en el almacén de certificados, consulte [utilidad de Asistente de certificado](http://go.microsoft.com/fwlink/?LinkId=155157) (<http://go.microsoft.com/fwlink/?LinkId=155157>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  

4. Hacer que el asociado se instale el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] certificado de clave pública para comprobar la firma digital en el almacén adecuado. Si el socio comercial usa Windows 2000 Server, Windows Server 2003 o Windows Server 2008, debe instalar la clave pública en el almacén otras personas.
