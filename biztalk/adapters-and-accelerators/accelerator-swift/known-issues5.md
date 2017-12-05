---
title: Conoce Issues5 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, known issues
- BizTalk Accelerator for SWIFT, known issues
- known issues
ms.assetid: 0f1ec7dd-9e74-479a-bdc8-ab9c4397c992
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1356209f700fc7ceff220f4b0f8fcd3dd67db07
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues"></a>Problemas conocidos
Esta sección contiene información útil que puede ayudar a evitar errores con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]. Los problemas conocidos se agrupan en las siguientes áreas:  
  
## <a name="message-repair-and-new-submission"></a>Reparación de mensajes y nuevo envío

#### <a name="printing-of-a-repair-document-is-recorded-in-the-history-log-even-if-canceled"></a>Impresión de un documento de reparación se registra en el registro de historial, incluso si se cancela  
 Si ejecuta el comando de impresión para un documento en la Bandeja de entrada de reparación y, a continuación, cancelar la impresión, la impresión continúa introduciéndose en el registro de historial. Esto se produce cuando se abre el documento que se desean reparar en su [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario, haga clic en el comando de impresión en el menú archivo y, a continuación, haga clic en Cancelar en el cuadro de diálogo Imprimir. Se debe omitir la entrada en el registro de historial.  
  
#### <a name="a-duplicate-signature-can-cause-an-xlangs-error-message"></a>Una firma duplicada puede provocar un mensaje de error XLANG/s  
 Cuando un comprobador utiliza el mismo certificado como un taller de reparación, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] suspende el mensaje y se indica en un mensaje de error que no se permiten duplicadas firmas. Sin embargo, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] también genera otro mensaje de error con un origen de eventos de XLANG/s, que indica que el servicio XLANG/s se ha suspendido. Puede ignorar este mensaje.  
  
#### <a name="message-size-can-affect-repair-performance"></a>Tamaño del mensaje puede afectar al rendimiento de reparación  
 Si intenta reparar un archivo XML extraordinariamente grande, el rendimiento del sistema puede degradar significativamente el al abrir el archivo XML en el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario para el tipo de mensaje. Puede aumentar el consumo de memoria, puede reducir el consumo de CPU y el proceso se puede producir un error que indica que no hay suficiente almacenamiento estaba disponible para completar la operación.  
  
#### <a name="the-last-signature-used-to-sign-a-message-successfully-will-be-authenticated-by-authenticate-signatures"></a>La última firma utilizada para firmar un mensaje correctamente se autenticarán autenticar firmas  
 Haga clic en el botón autenticar firmas en un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario valida la firma para el escenario que estás en solo si ya han iniciado sesión el formulario. En caso contrario, valida la firma para la fase anterior, si hay alguna y registra el error siguiente:  
  
 El usuario firmado no está configurado correctamente para el rol < stage_name > en < department_name > de departamento.  
  
 Por ejemplo, suponga que se encuentra en una fase de aprobar inmediatamente después de una fase de comprobación. Si no ha firmado el formato que el aprobador y haga clic en autenticar firmas, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] autentica la firma que el Comprobador utiliza, no firma del aprobador y registra el error anterior.  

#### <a name="a4swift-cleanup-tool-doesnt-delete-templates"></a>Herramienta de limpieza de A4SWIFT no elimina las plantillas  
 La herramienta de limpieza de A4SWIFT no realiza las siguientes operaciones:  
  
-   Quita todas las plantillas de MT de sitio MRSR  
  
-   Quita todos los acuerdos y perfiles de socios comerciales de sitio MRSR  
  
-   Quita todos los usuarios, roles y departamentos  
  
-   Anula el registro de A4SWIFT BizTalk Server desde el sitio MRSR  
  
#### <a name="the-a4swiftmrsrdepartment-property-is-set-to-an-empty-string-for-a-message-that-did-not-parse"></a>La propiedad A4SWIFT_MRSRDepartment se establece en una cadena vacía para un mensaje que no se analizó  
 Cuando la orquestación de reparación de mensajes enruta al cuadro de mensajes un mensaje sin analizar que se ha corregido, establecerá el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_MRSRDepartment propiedad vacío de cadena y promoverlo. Un puerto de envío no podrá suscribirse en esta propiedad.  
  
#### <a name="cannot-save-a-department-if-the-sso-service-has-been-stopped"></a>No se puede guardar un departamento si se ha detenido el servicio SSO  
 Si intenta agregar un departamento cuando se detiene el servicio SSO, recibirá un error que indica que el servidor de SSO principal \<machinename\> error. Compruebe si SSO está configurado y si el servicio SSO está en ejecución en ese servidor.  
  
#### <a name="a-department-name-must-not-contain-the-character-"></a>Nombre de un departamento no debe contener el carácter "~"  
 Un nombre de departamento que contiene el carácter "~" dará lugar a problemas con la base de datos de A4SWIFT.  
  
#### <a name="signing-infopath-forms"></a>Firma de formularios de Infopath  
 La firma de formularios de InfoPath debe realizarse manualmente.  
  
## <a name="security"></a>Seguridad

#### <a name="mixing-trusted-and-untrusted-hosts-can-enable-spoofing"></a>Combinación de hosts de confianza y puede habilitar la suplantación de identidad  

 Es posible suplantar la identidad de mensajes de SWIFT enlazados desde otros no es de confianza [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] hospedar aplicaciones. Esto es sólo un problema cuando se ejecuta en modo de confianza mixto (cuando los hosts de confianza y confianza ejecutan aplicaciones en el mismo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo). Puede mitigar este riesgo mediante el uso de componentes de canalización de resolución de entidades para identificar el origen del mensaje SWIFT enlazado. Esto no es necesario cuando se ejecuta en un entorno de plena confianza o en la mayoría de los escenarios de uso. Debe seguir el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] directrices para crear aplicaciones seguras cuando se mezclan de confianza y no los hosts de confianza. 
 
## <a name="miscellaneous"></a>Varios

#### <a name="the-cacheentries-setting-may-be-reset-by-a-setup-program-affecting-performance"></a>Puede restablecer el valor de CacheEntries por un programa de instalación, que afectan al rendimiento  
 La clave del registro de CacheEntries determina el número máximo de conjuntos de reglas que se almacenan en caché por el servicio de actualización de motor de reglas de negocios. El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] programa de instalación establece CacheEntries 32 de forma predeterminada. El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] programa de instalación cambia HKEY_LOCAL_MACHINE\SOFTWARE\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]\BusinessRules\3.0\CacheEntries a 512 para un rendimiento óptimo. Sin embargo, en ciertas circunstancias, CacheEntries puede restablecerse automáticamente. Esto puede afectar al rendimiento.  
  
 Actualizaciones de motor de reglas pueden cambiar CacheEntries de 512 a 32. Después de instalar una actualización de motor de reglas, restablecer manualmente CacheEntries a 512, si es necesario.  
  
 Aunque la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] programa de instalación establece CacheEntries desde 32 hasta 512, desinstalar [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no restablece CacheEntries de 512 a 32.  
  
 Para obtener más información, vea el tema "Regla motor y ajustar parámetros de configuración" en la Ayuda de BizTalk Server.  
  
#### <a name="building-a-pipeline-project-may-result-in-a-large-number-of-warnings"></a>Compilar un proyecto de canalización puede dar lugar a un gran número de advertencias  
 Al agregar el ensamblador SWIFT a una canalización de envío o el Desensamblador SWIFT a una canalización de recepción y, a continuación, compile el proyecto de canalización que contiene esas canalizaciones, recibirá una serie de advertencias relacionadas con los componentes de canalización. Estas advertencias indican que Visual Studio no pudo encontrar las dependencias. Puede corregir la condición que conduce a estas advertencias cambiando la propiedad Copy Local del ensamblado SWIFTAsm o SWIFTDasm en la carpeta de referencia, como se indica a continuación:  
  
1.  En el Explorador de soluciones de Visual Studio, expanda el proyecto de canalización y, a continuación, expanda el **referencias** nodo.  
  
2.  En el nodo referencias, seleccione la **SWIFTAsm** ensamblado o **SWIFTDasm** ensamblado.  
  
3.  En el panel Propiedades, cambie el valor de la **Copy Local** propiedad **False**.  
  
4.  Haga clic en el proyecto de canalización y, a continuación, haga clic en **generar**.  
  
    > [!NOTE]
    >  No debería ver las advertencias sobre las dependencias que no se encuentre.   