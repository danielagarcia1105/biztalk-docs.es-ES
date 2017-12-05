---
title: "Paso 1: Crear una entidad de certificación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, creating
- double action tutorial, creating certificates
- creating, certificates
ms.assetid: b6ecd534-6b03-4336-8337-33ec18a0802a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3d796608a4cc323ccf5e1a8bdee7420c5bab259
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-creating-a-certification-authority"></a>Paso 1: Crear una entidad de certificación
En este tema, instale los servicios de Certificate Server [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componente. Usarlo para generar los certificados que necesita para promover una comunicación segura entre las organizaciones de Contoso y Fabrikam. Todos los socios comerciales tendrá un certificado de cifrado privada para la comunicación y el certificado de firma privada para propósitos de identificación. Además, los socios compartirán sus certificados de clave pública entre sí para promover una comunicación segura al implementar el proceso de interfaz de socio (PIP) 3A2.  
  
### <a name="to-install-the-certificate-server"></a>Para instalar al servidor de certificados  
  
1.  Haga clic en **iniciar**, seleccione **configuración**y, a continuación, haga clic en **el Panel de Control**. Haga doble clic en **agregar o quitar programas**.  
  
2.  En el **agregar o quitar programas** cuadro de diálogo, haga clic en **agregar o quitar componentes de Windows**.  
  
3.  En el **Asistente para componentes de Windows** página, en la **componentes** sección, seleccione **servicios de Certificate Server**, haga clic en **Sí**y, a continuación, haga clic en **Siguiente** para iniciar el Asistente para la configuración de componentes.  
  
    > [!NOTE]
    >  Si el **ServicesWindows certificados** componente ya está seleccionado, omita el resto de este procedimiento.  
  
4.  En el **el tipo de CA** página, asegúrese de que **entidad emisora raíz independiente** está seleccionada y, a continuación, haga clic en **siguiente**.  
  
5.  En el **información de identificación de la entidad emisora de certificados** página, en la **nombre común para esta entidad de certificación** , escriba **Contoso FabrikamCA**y, a continuación, haga clic en **siguiente**.  
  
6.  En el **configuración de base de datos de certificados** página, deje los valores predeterminados y, a continuación, haga clic en **siguiente**.  
  
7.  Haga clic en **Sí** cuando el asistente le pregunta si desea detener los servicios de Internet Information Server (IIS).  
  
8.  Haga clic en **Sí** si la **Asistente para componentes de la configuración** le solicita que habilite las páginas Active Server.  
  
9. Haga clic en **finalizar** para cerrar el **Asistente para componentes de Windows**.  
  
    > [!NOTE]
    >  Solamente debe usar un equipo como la entidad de certificación. No es necesario repetir este paso en el segundo equipo. Este tutorial usa el equipo de Contoso como la entidad de certificación.  
  
### <a name="to-install-a-root-certification-authority-ca-for-windows-server-2008"></a>Para instalar una entidad de certificación (CA) raíz de Windows Server 2008  
  
1.  Abra Administrador del servidor, haga clic en **agregar Roles** en Roles, haga clic en **siguiente**y haga clic en **certificados de Active Directory** casilla de verificación de servicios. Haga clic en **siguiente** dos veces.  
  
2.  En la página Seleccionar servicios de rol, haga clic en **entidad emisora de certificados y la inscripción Web de entidad de certificación**. Haga clic en **Siguiente**.  
  
3.  En la página Especificar tipo de instalación, haga clic en **independiente**. Haga clic en **Siguiente**.  
  
4.  En la página especificar el tipo de entidad emisora de certificados, haga clic en la entidad de certificación raíz. Haga clic en **Siguiente**.  
  
5.  En la página Configurar clave privada, haga clic en crear una nueva clave privada. Haga clic en **Siguiente**.  
  
6.  En la criptografía configurar para la página de la entidad emisora de certificados. Haga clic en **Siguiente**.  
  
7.  Configurar el nombre de entidad emisora de certificados, en el cuadro Nombre común para esta entidad emisora de certificados, escriba Contoso FabrikamCA y, a continuación, haga clic en **siguiente**.  
  
8.  En la página establecer el período de validez, haga clic en **siguiente**.  
  
9. En la página Configurar base de datos de certificados, haga clic en **siguiente**.  
  
10. En la página Confirmar opciones de instalación, haga clic en **instalar**.  
  
### <a name="configuring-the-web-site-for-the-ca-to-use-https-authentication"></a>Configurar el sitio Web de la CA para que use autenticación HTTPS  
  
1.  En el equipo en el que se utiliza como la entidad de certificación, haga clic en Inicio, seleccione todos los programas, herramientas administrativas y, a continuación, haga clic en Administrador de Internet Information Services (IIS).  
  
2.  En el cuadro de diálogo Administrador de Internet Information Services (IIS), haga clic en **sitio Web predeterminado y seleccione Modificar enlaces...** en el menú emergente.  
  
3.  En el cuadro de diálogo de enlaces de sitios, haga clic en **agregar**.  
  
4.  En el cuadro de diálogo Agregar enlace de sitio seleccione **https** en la lista desplegable Tipo, seleccione el certificado de **certificado SSL** de lista desplegable y haga clic en **Aceptar**.  
  
5.  Haga clic en **cerrar** para cerrar los enlaces de sitio... cuadro de diálogo.  
  
### <a name="to-download-the-ca-certificate"></a>Para descargar el certificado de CA  
  
1.  En Internet Explorer, busque y abra http://<contoso_computername>/certsrv/Default.asp.  
  
2.  En la página Default.asp, haga clic en **descargar un certificado de CA, cadena de certificados o CRL**.  
  
3.  Asegúrese de que **actual [Contoso-FabrikamCA]** está seleccionado en el **certificado de CA** lista y, a continuación, haga clic en **Descargar certificado de entidad emisora de certificados**.  
  
4.  Guarde el certificado en C:\Certs\Contoso-FabrikamCA.cer en el de Contoso y el equipo de Fabrikam.  
  
### <a name="to-import-the-ca-certificate-to-the-trusted-root-certification-authorities-store"></a>Para importar el certificado de CA en el almacén de entidades de certificación raíz de confianza  
  
1.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
2.  En el símbolo del sistema, vaya a  **\<unidad\>: \Program Files\MicrosoftBizTalk \<versión\> Accelerator for RosettaNet\SDK**y, a continuación, presione **ENTRAR**.  
  
3.  En el símbolo del sistema, escriba **CertWizard /Rootkey "\<unidad\>: \Certs\Contoso-FabrikamCA.cer"**y, a continuación, presione **ENTRAR**.  
  
    > [!IMPORTANT]
    >  Llevar a cabo este procedimiento en los equipos de Contoso y Fabrikam.  
  
### <a name="to-enable-automatic-certificate-issuing"></a>Para habilitar la emisión automática de certificados  
  
1.  En el equipo en el que se utiliza como la entidad de certificación, haga clic en **iniciar**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en  **Entidad de certificación**.  
  
2.  En el cuadro de diálogo entidad de certificación, haga clic en **Contoso FabrikamCA**y, a continuación, haga clic en **propiedades**.  
  
3.  En el cuadro de diálogo Propiedades de Contoso-FabrikamCA, en la **módulo de directivas** , haga clic en **propiedades**.  
  
4.  En el cuadro de diálogo Propiedades, seleccione **seguir la configuración de la plantilla de certificado**y, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo FabrikamCA de Contoso.  
  
6.  Cierre el cuadro de diálogo de la entidad de certificación.  
  
    > [!NOTE]
    >  Al habilitar la emisión de certificados automática, servicios de Certificate Server automatiza el procedimiento de emisión de certificados. Tendrá que reiniciar los servicios de Certificate Server para aplicar este cambio.  
    >   
    >  Debe instalar el certificado raíz Contoso-FabrikamCA.cer en las entidades de certificación de raíz de User\Trusted actual.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Crear certificados públicos y privados](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)