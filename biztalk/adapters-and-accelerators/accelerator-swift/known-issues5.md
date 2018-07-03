---
title: Conoce Issues5 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, known issues
- BizTalk Accelerator for SWIFT, known issues
- known issues
ms.assetid: 0f1ec7dd-9e74-479a-bdc8-ab9c4397c992
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7c164e8c0d6713389fd317c8839d72770f07c56
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000557"
---
# <a name="known-issues"></a>Problemas conocidos
Esta sección contiene información útil que puede ayudar a evitar errores con Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]. Los problemas conocidos se agrupan en las áreas siguientes:  
  
## <a name="message-repair-and-new-submission"></a>Reparación de mensajes y nuevo envío

#### <a name="printing-of-a-repair-document-is-recorded-in-the-history-log-even-if-canceled"></a>Impresión de un documento de reparación se registra en el registro de historial, incluso si se cancela  
 Si ejecuta el comando de impresión para un documento en la Bandeja de entrada de reparación y, a continuación, cancelar la impresión, la impresión continúa introduciéndose en el registro de historial. Esto se produce cuando se abre el documento que se va a ser reparado en su [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] de formulario, haga clic en el comando de impresión en el menú archivo y, a continuación, haga clic en Cancelar en el cuadro de diálogo Imprimir. Debe omitir la entrada en el registro de historial.  
  
#### <a name="a-duplicate-signature-can-cause-an-xlangs-error-message"></a>Una firma de duplicados puede provocar un mensaje de error XLANG/s  
 Cuando un comprobador utiliza el mismo certificado como un taller de reparación, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] suspende el mensaje e indica un mensaje de error que no se permiten duplicadas firmas. Sin embargo, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] también genera otro mensaje de error con un origen de eventos de XLANG/s, que indica que el servicio XLANG/s se ha suspendido. Puede ignorar este mensaje.  
  
#### <a name="message-size-can-affect-repair-performance"></a>Tamaño del mensaje puede afectar al rendimiento de reparación  
 Si intenta reparar un archivo XML inusualmente grande, puede disminuir considerablemente el rendimiento del sistema al abrir el archivo XML en el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario para el tipo de mensaje. Puede aumentar el consumo de memoria, puede reducir el consumo de CPU y el proceso puede producir un error que indica que no hay suficiente almacenamiento estaba disponible para completar la operación.  
  
#### <a name="the-last-signature-used-to-sign-a-message-successfully-will-be-authenticated-by-authenticate-signatures"></a>La última firma utilizada para firmar un mensaje correctamente se autenticará con firmas autenticar  
 Al hacer clic en el botón autenticar firmas en un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario valida la firma para el escenario que se encuentra solo si ya ha firmado el formulario. En caso contrario, valida la firma para el escenario anterior, si hay alguna y registra el error siguiente:  
  
 El usuario de la firmado no está configurado correctamente para el rol < stage_name > en < department_name > del departamento.  
  
 Por ejemplo, suponga que se encuentra en una fase aprobar inmediatamente después de una fase de comprobación. Si aún no se ha registrado el formulario como aprobador y haga clic en las firmas de autenticarse, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] autentica la firma que utiliza el Comprobador de, no firma del aprobador y registra el error anterior.  

#### <a name="a4swift-cleanup-tool-doesnt-delete-templates"></a>Herramienta de limpieza de A4SWIFT no elimina las plantillas  
 La herramienta de limpieza de A4SWIFT no lleva a cabo las siguientes operaciones:  
  
-   Quita todas las plantillas de MT sitio MRSR  
  
-   Quita todos los acuerdos y perfiles de socios comerciales del sitio MRSR  
  
-   Quita todos los usuarios, roles y los departamentos de TI  
  
-   Anula el registro de BizTalk Server desde el sitio MRSR A4SWIFT  
  
#### <a name="the-a4swiftmrsrdepartment-property-is-set-to-an-empty-string-for-a-message-that-did-not-parse"></a>La propiedad A4SWIFT_MRSRDepartment se establece en una cadena vacía para un mensaje que no se analizó  
 Cuando la orquestación de reparación de mensajes enruta al cuadro de mensajes de un mensaje sin analizar que se ha corregido, establecerá el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_MRSRDepartment propiedad a un valor vacío de cadena y promoverlo. Un puerto de envío no podrá suscribirse en esta propiedad.  
  
#### <a name="cannot-save-a-department-if-the-sso-service-has-been-stopped"></a>No se puede guardar un departamento si se ha detenido el servicio de inicio de sesión único  
 Si intenta agregar un departamento cuando se detiene el servicio de inicio de sesión único, recibirá un error que indica que el servidor de SSO principal \<machinename\> error. Compruebe si SSO está configurado y si el servicio SSO está en ejecución en ese servidor.  
  
#### <a name="a-department-name-must-not-contain-the-character-"></a>Nombre de un departamento no debe contener el carácter "~"  
 Un nombre de departamento que contiene el carácter "~" dará lugar a problemas con la base de datos de A4SWIFT.  
  
#### <a name="signing-infopath-forms"></a>Firma de formularios de Infopath  
 La firma de formularios de InfoPath debe realizarse manualmente.  
  
## <a name="security"></a>Seguridad

#### <a name="mixing-trusted-and-untrusted-hosts-can-enable-spoofing"></a>Combinación de hosts de confianza y puede habilitar la suplantación de identidad  

 Es posible suplantar la identidad de los mensajes de SWIFT enlazados de otros que no son de confianza [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] hospedar aplicaciones. Esto es solo un problema cuando se ejecuta en modo de confianza mixto (cuando los hosts de confianza y confianza ejecutan aplicaciones en la misma [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo). Puede mitigar este riesgo mediante el uso de los componentes de canalización de resolución de entidades para identificar el origen del mensaje SWIFT enlazados. Esto no es necesario cuando se ejecuta en un entorno de plena confianza o para la mayoría de escenarios de uso. Debe seguir el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] directrices para crear aplicaciones seguras al mezclar de confianza y hosts de confianza. 
 
## <a name="miscellaneous"></a>Varios

#### <a name="the-cacheentries-setting-may-be-reset-by-a-setup-program-affecting-performance"></a>Puede restablecer el valor de CacheEntries por un programa de instalación, que afectan al rendimiento  
 La clave del registro de CacheEntries determina el número máximo de conjuntos de reglas que se almacenan en caché por el servicio de actualización de motor de reglas de negocio. El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] programa de instalación establece CacheEntries a 32 de forma predeterminada. El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] programa de instalación cambia HKEY_LOCAL_MACHINE\SOFTWARE\\Microsoft \BusinessRules\3.0\CacheEntries a 512 para un rendimiento óptimo. Sin embargo, en determinadas circunstancias, CacheEntries pueden restablecerse automáticamente. Esto puede afectar al rendimiento de sistema.  
  
 Actualizaciones de motor de reglas pueden cambiar CacheEntries de 512 a 32. Después de instalar una actualización de motor de reglas, restablecer manualmente CacheEntries a 512, si es necesario.  
  
 Aunque el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] programa de instalación establece CacheEntries de 32 a 512, desinstalar [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no restablece CacheEntries de 512 a 32.  
  
 Para obtener más información, vea el tema "Regla motor y ajustar parámetros de configuración" en la Ayuda de BizTalk Server.  
  
#### <a name="building-a-pipeline-project-may-result-in-a-large-number-of-warnings"></a>Creación de un proyecto de canalización puede provocar un gran número de advertencias  
 Al agregar el ensamblador de SWIFT a una canalización de envío o del desensamblador de SWIFT a una canalización de recepción y, a continuación, compile el proyecto de canalización que contiene las tuberías, recibirá una serie de advertencias relacionadas con los componentes de canalización. Estas advertencias indican que Visual Studio no pudo encontrar las dependencias. Puede corregir la condición que conduce a estas advertencias cambiando la propiedad Copy Local del ensamblado SWIFTAsm o SWIFTDasm en la carpeta de referencia, como sigue:  
  
1.  En el Explorador de soluciones de Visual Studio, expanda el proyecto de canalización y, a continuación, expanda el **referencias** nodo.  
  
2.  En el nodo referencias, seleccione el **SWIFTAsm** ensamblado o el **SWIFTDasm** ensamblado.  
  
3.  En el panel Propiedades, cambie el valor de la **Copy Local** propiedad **False**.  
  
4.  Haga clic en el proyecto de canalización y, a continuación, haga clic en **compilar**.  
  
    > [!NOTE]
    >  No debería ver las advertencias sobre las dependencias no se encuentre.   