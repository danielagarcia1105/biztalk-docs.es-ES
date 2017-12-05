---
title: "Tutorial: Crear una aplicación de BizTalk que utiliza el adaptador de POP3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tutorials, POP3 adapters
- configuring [POP3 adapters], mailboxes
- configuring [POP3 adapters], tutorials
- POP3 adapters, mailboxes
- POP3 adapters, tutorials
- configuring [POP3 adapters], Outlook Express
ms.assetid: b44c3b1d-7b4f-425c-831a-1ce5f6379595
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e677a4fb68ad4f6991585c191c8065a60b3fc337
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter"></a>Tutorial: Crear una aplicación de BizTalk que usa el adaptador de POP3
Esta sección muestra cómo crear una aplicación sencilla de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el adaptador de POP3.  
  
> [!NOTE]
>  La aplicación supone que tiene acceso al equipo que ejecuta Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] con los servicios de correo electrónico instalados y configurados. Para obtener información sobre la configuración de [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] con los servicios de correo electrónico, consulte la ayuda de Windows Server.  
  
> [!NOTE]
>  En este ejemplo, se usa Microsoft Outlook Express como cliente de correo electrónico y [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] se usan como servidor de correo electrónico. Sin embargo, para este escenario se podría utilizar cualquier cliente de correo electrónico POP3 y servidor POP3 que cumpla con RFC.  
  
 Esta aplicación supone que todavía no ha creado ningún puerto de envío o ubicación de recepción. Si dispone de puertos de envío o ubicaciones de recepción existentes, sustituya los nombres correspondientes cuando siga los pasos.  
  
 La aplicación es una sencilla aplicación de enrutamiento por contenidos que sólo utiliza un puerto de envío o una ubicación de recepción. La ubicación de recepción lee de un buzón en el servidor que ejecuta [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("el servidor de Windows"\). El puerto de envío toma el mensaje de la ubicación de recepción y lo envía a la carpeta del sistema de archivos local de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Para crear la aplicación, debe crear el buzón, configurar el puerto de envío y la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], iniciar el puerto de envío, habilitar la ubicación de recepción y enviar un mensaje al buzón. Para crear la aplicación, siga los pasos que se indican a continuación.  
  
## <a name="create-a-mailbox-on-windows-server-2003"></a>Crear un buzón en Windows Server 2003  
 Para crear un buzón en Windows Server 2003 con servicios de correo electrónico instalados, siga estos pasos:  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **servicio POP3**.  
  
2.  Expanda  *\<servername\>*  y haga clic en el dominio donde desea crear un buzón.  
  
3.  En el **servicio POP3** cuadro de diálogo, en el panel derecho, haga clic en el **Agregar buzón** opción.  
  
4.  En el **Agregar buzón** cuadro de diálogo, en la **nombre del buzón** , escriba **EmailTest**.  
  
5.  Seleccione el **crear un usuario asociado para este buzón** casilla de verificación.  
  
6.  En el **contraseña** y **Confirmar contraseña** cuadros, escriba una contraseña y, a continuación, haga clic en **Aceptar**.  
  
7.  Tome nota de la **nombre de la cuenta** y **servidor de correo** inicie sesión en la información que se muestra para su uso con la autenticación de texto no cifrado en el **servicio POP3** cuadro de diálogo y, a continuación, haga clic en **Aceptar**. La ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que configure con el tipo de transporte POP3 usará esta información.  
  
## <a name="create-the-receive-location"></a>Crear la ubicación de recepción  
 Para crear la ubicación de recepción, siga estos pasos:  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga doble clic en la base de datos predeterminada  **\<**  *nombre_equipo***\>. BizTalkMgmtDb.dbo**, donde *nombre_equipo* es el nombre del equipo. Haga clic en **aplicaciones**, a continuación, haga clic en **BizTalk.Application.1**.  
  
2.  Haga clic en **puertos de recepción**, haga clic en **New**, haga clic en **unidireccional puerto de recepción**.  
  
3.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **nombre** , escriba **POP3Receive**.  
  
4.  Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **nuevo**.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba **POP3Receive**.  
  
5.  En el **tipo de transporte** cuadro, seleccione **POP3**.  
  
6.  En el **controlador de recepción** cuadro, seleccione **BizTalkServerApplication**.  
  
7.  En el **canalización de recepción** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.  
  
8.  En el **transporte** cuadro, haga clic en el **configurar** botón.  
  
9. En el **propiedades de transporte POP3** cuadro de diálogo, en la **aplicar descodificación MIME** cuadro, seleccione **False**.  
  
10. En el **servidor de correo electrónico** , escriba el nombre del servidor basado en Windows Server donde creó un buzón.  
  
11. En el **esquema de autenticación** cuadro, seleccione **básica**.  
  
12. En el **contraseña** cuadro, haga clic en la flecha de lista desplegable y escriba la contraseña del buzón.  
  
13. En el **nombre de usuario** , escriba el nombre de usuario completo para el buzón, por ejemplo  *username@host.domain.toplevel_domain.*  
  
14. En el **intervalo de sondeo** , escriba **1**, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
## <a name="create-the-send-port-and-destination-folder-on-the-biztalk-server"></a>Crear la carpeta de puerto de envío y de destino en el servidor BizTalk Server  
 Siga estos pasos para crear el puerto de envío y la carpeta de destino en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
1.  Cree una carpeta en el sistema de archivos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Éste será el destino del puerto de envío.  
  
2.  Haga clic en **puertos de envío**, haga clic en **nuevo** , a continuación, haga clic en **puerto de envío unidireccional estático.**  
  
3.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **tipo de transporte** cuadro, seleccione **archivo**.  
  
4.  En el **nombre** , escriba **SendToFile**.  
  
5.  En el **transporte** cuadro, haga clic en el **configurar** botón.  
  
6.  Junto a la **carpeta de destino** cuadro, haga clic en **examinar**, seleccione la carpeta que creó en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y, a continuación, haga clic en **Aceptar**.  
  
7.  En el **nombre de archivo** , escriba **%MessageID%.txt**y, a continuación, haga clic en **Aceptar**.  
  
8.  En el **canalización de envío** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.  
  
9. Haga clic en **Filtros**.  
  
10. En el **propiedad** cuadro, seleccione **BTS. ReceivePortName**.  
  
11. En el **valor** , escriba **POP3Receive**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="enable-the-receive-location-and-start-the-send-port"></a>Habilitar la ubicación de recepción e iniciar el puerto de envío  
 Para habilitar la ubicación de recepción e iniciar el puerto de envío, siga estos pasos:  
  
1.  Haga clic en el **POP3Receive** ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
2.  Haga clic en el **SendToFile** puerto de envío y, a continuación, haga clic en **iniciar**.  
  
 El paso siguiente es probar la aplicación mediante el envío de un mensaje de prueba al buzón supervisado mediante la ubicación de recepción.  
  
## <a name="configure-outlook-express-to-send-an-e-mail-message-to-the-mailbox"></a>Configurar Outlook Express para enviar un mensaje de correo electrónico al buzón  
 Para configurar Outlook Express para enviar un mensaje de correo electrónico al buzón, siga estos pasos:  
  
1.  Haga clic en **iniciar**, seleccione **programas**y, a continuación, haga clic en **Outlook Express**.  
  
2.  En Outlook Express, en el **herramientas** menú, haga clic en **cuentas**.  
  
3.  Haga clic en **agregar** y, a continuación, haga clic en **correo**.  
  
4.  En el **nombre para mostrar** , escriba un nombre para mostrar y, a continuación, haga clic en **siguiente**.  
  
5.  En el **dirección de correo electrónico de Internet** cuadro de diálogo, en la **dirección de correo electrónico** , escriba **EmailTest @< nombreDeDominio >**y, a continuación, haga clic en **siguiente**.  
  
     Asegúrese de escribir el valor adecuado para *< nombreDeDominio >*. Este valor debe coincidir con el nombre de dominio en el que se creó este buzón en la interfaz de administración de servicio POP3 en el servidor Windows.  
  
6.  En el **nombres de servidor de correo electrónico** cuadro de diálogo, en la **correo entrante** y **correo saliente** cuadros, escriba el nombre del servidor o dirección IP del servidor de Windows y, a continuación, haga clic en  **Siguiente**.  
  
7.  En el **inicio de sesión de correo de Internet** cuadro de diálogo, en la **nombre de la cuenta** , escriba **EmailTest**.  
  
8.  En el **contraseña** , escriba la contraseña de la cuenta EmailTest, seleccione la **recordar contraseña** opción, haga clic en **siguiente**y, a continuación, haga clic en **finalizar**.  
  
9. Haga clic para seleccionar la cuenta que acaba de crear y, a continuación, haga clic en **propiedades**.  
  
10. En el **propiedades** cuadro de diálogo, haga clic en el **avanzadas** , haga clic para seleccionar la opción de **dejar una copia de los mensajes en el servidor**y, a continuación, haga clic en **Aceptar**.  
  
11. En el **cuentas de Internet** cuadro de diálogo, haga clic en **cerrar**.  
  
12. Use Outlook Express para redactar un mensaje de prueba, tipo **probar** en el **asunto** campo y escriba **EmailTest @< nombreDeDominio >** en la **a** campo.  
  
13. Haga clic en **enviar** para enviar el mensaje de prueba. Para asegurarse de que Outlook Express envía el mensaje de prueba inmediatamente, haga clic en el **enviar/recibir** botón en la barra de herramientas de Outlook Express.  
  
## <a name="view-the-message"></a>Ver el mensaje  
 Para ver el mensaje, siga estos pasos:  
  
1.  Utilice el Explorador de Windows para abrir la carpeta que especificó como la **carpeta de destino** del puerto de envío.  
  
2.  Haga doble clic en el documento de la carpeta para ver el contenido del documento en el Bloc de notas.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es el adaptador de POP3?](../core/what-is-the-pop3-adapter.md)