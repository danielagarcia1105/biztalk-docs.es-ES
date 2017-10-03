---
title: 'Paso 2: Crear Public y Private certificados | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating certificates
- public certificates
- certificates, public certificates
- creating, certificates
- private certificates
ms.assetid: 0a925d89-03d9-41fe-907b-85a6ae42362a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d9653f1ec72e56b225142d2d6c9fdff24198e7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-creating-public-and-private-certificates"></a>Paso 2: Crear Public y Private certificados
En este paso, utilice la entidad de certificación que se creó en [paso 1: crear una entidad de certificación &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md) para generar los certificados públicos y privados que utilizan las organizaciones de Contoso y Fabrikam.  
  
### <a name="to-generate-the-contoso-and-fabrikam-encryption-certificates"></a>Para generar los certificados de cifrado de Contoso y Fabrikam  
  
1.  En el equipo que utiliza como la entidad de certificación, en Internet Explorer, busque y abra http://<contoso_computername>/certsrv.  
  
2.  En el **bienvenida** página, haga clic en **solicitar un certificado**.  
  
3.  En el **solicitar un certificado** página, haga clic en **solicitud de certificado avanzada**.  
  
4.  En el **solicitud de certificado avanzada** página, haga clic en **crear y enviar una solicitud a esta CA**.  
  
5.  En el **solicitud de certificado avanzada** página, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **Fabrikam cifrado**.|  
    |**Correo electrónico**|Tipo de  **jdoe@fabrikam.com** .|  
    |**Compañía**|Tipo de **Fabrikam**.|  
    |**Departamento**|Tipo de **prueba**.|  
    |**City**|Tipo de **prueba**.|  
    |**State**|Tipo de **prueba**.|  
    |**País o región**|Tipo de **US**.|  
    |**Tipo de certificado necesario**|Seleccione **certificado de protección de correo electrónico** desde la lista desplegable.|  
    |**Uso de claves**|Seleccione el **Exchange** opción.|  
    |**Opciones de clave adicionales**|Marque las siguientes opciones:<br /><br /> -   **Marcar esta clave como exportable**<br />-   **Almacenar el certificado en el almacén de certificados del equipo local**|  
    |**Nombre descriptivo**|Tipo de **Fabrikam cifrado**.|  
  
6.  Haga clic en **enviar**y, a continuación, haga clic en **Sí** en **confirmación de acceso Web** cuadro de diálogo.  
  
7.  En el **certificado emitido** página, haga clic en **instalar este certificado**.  
  
8.  Repita los pasos 1-7, cambiar la información de la **nombre** cuadro el **información de identificación de** sección y la **Nombre_descriptivo** cuadro a **Contoso Cifrado**.  
  
### <a name="to-generate-the-contoso-and-fabrikam-signing-certificates"></a>Para generar los Contoso y Fabrikam certificados de firma  
  
1.  En Internet Explorer, busque y abra http://<contoso_computername>/certsrv.  
  
2.  En el **bienvenida** página, haga clic en **solicitar un certificado**.  
  
3.  En el **solicitar un certificado** página, haga clic en **solicitud de certificado avanzada**.  
  
4.  En el **solicitud de certificado avanzada** página, haga clic en **crear y enviar una solicitud a esta CA**.  
  
5.  En el **solicitud de certificado avanzada** página, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **Fabrikam firma**.|  
    |**Correo electrónico**|Tipo de  **jdoe@fabrikam.com** .|  
    |**Compañía**|Tipo de **Fabrikam**.|  
    |**Departamento**|Tipo de **prueba**.|  
    |**City**|Tipo de **prueba**.|  
    |**State**|Tipo de **prueba**.|  
    |**País o región**|Tipo de **US**.|  
    |**Tipo de certificado necesario**|Seleccione **certificado de protección de correo electrónico**.de la lista desplegable.|  
    |**Uso de claves**|Seleccione el **firma** opción.|  
    |**Opciones de clave adicionales**|Marque las siguientes opciones:<br /><br /> -   **Marcar esta clave como exportable**<br />-   **Almacenar el certificado en el almacén de certificados del equipo local**|  
    |**Nombre descriptivo**|Tipo de **Fabrikam firma**.|  
  
6.  Haga clic en **enviar**y, a continuación, haga clic en **Sí** cuando se le pregunte para solicitar el certificado.  
  
7.  En el **certificado emitido** página, haga clic en **instalar este certificado**.  
  
8.  Repita los pasos 1-7, cambiar la información de la **nombre** cuadro el **información de identificación de** sección y la **Nombre_descriptivo** cuadro a **Contoso Firma**.  
  
### <a name="to-generate-private-certificates-for-the-encryption-and-signature-certificates"></a>Para generar certificados privados para los certificados de firma y cifrado  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **MMC**y, a continuación, haga clic en **Aceptar**.  
  
2.  En la ventana Consola1, en el **archivo** menú, haga clic en **agregar o quitar complemento**.  
  
3.  En el cuadro de diálogo Agregar o quitar complemento, en el **independiente** , haga clic en **agregar**.  
  
4.  En el cuadro de diálogo Add Standalone Snap-in, seleccione la **certificados** complemento desde la **complementos Standalone disponibles** lista y, a continuación, haga clic en **agregar**.  
  
5.  En el cuadro de diálogo del complemento de certificados, seleccione **mi cuenta de usuario**y, a continuación, haga clic en **siguiente**.  
  
6.  En el cuadro de diálogo Seleccionar equipo, haga clic en **finalizar**.  
  
7.  En el cuadro de diálogo Add Standalone Snap-in, haga clic en **cerrar**.  
  
8.  En el cuadro de diálogo Agregar o quitar complemento, haga clic en **Aceptar**.  
  
9. En la ventana Consola1, expanda **certificados (equipo Local)**, expanda **Personal**y, a continuación, haga clic en **certificados**.  
  
10. En el panel derecho, haga clic en el **Fabrikam cifrado** de certificados, seleccione **todas las tareas**y, a continuación, haga clic en **exportar**.  
  
11. En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.  
  
12. En el **exportar la clave privada** página, seleccione **Sí, exportar la clave privada**y, a continuación, haga clic en **siguiente**.  
  
13. En el **Exportar formato de archivo** página, asegúrese de que **Personal Information Exchange** es la única opción seleccionada y, a continuación, haga clic en **siguiente**.  
  
14. En el **contraseña** página, en la **contraseña** y **Confirmar contraseña** cuadros, escriba **MiSecreto**y, a continuación, haga clic en **siguiente** .  
  
15. En el **archivo de exportación** página, haga clic en **examinar**.  
  
16. En el **Guardar como** cuadro de diálogo, guarde el certificado con la ruta de acceso de archivo  *\<unidad >*: \Certs\Fabrikam Encryption.pfx privada.  
  
17. En el **archivo para exportar** página, haga clic en **siguiente**.  
  
18. En el **completar el Asistente para exportación de certificados** página, haga clic en **finalizar**.  
  
19. En la ventana emergente de Asistente para exportación de certificados que indica la exportación sea correcta, haga clic en **Aceptar**.  
  
20. Repita los pasos 10-19 para el certificado de firma de Fabrikam mediante el nombre de archivo Signature.pfx privada de Fabrikam.  
  
21. Repita los pasos 10-19 de los certificados de firma de Contoso y el cifrado de Contoso con los nombres de archivo Signature.pfx privada de Contoso y Encryption.pfx privada de Contoso, respectivamente.  
  
### <a name="to-generate-public-certificates-for-the-encryption-and-signature-certificates"></a>Para generar los certificados públicos para los certificados de firma y cifrado  
  
1.  En la ventana Consola1, expanda **certificados – usuario actual**, expanda **Personal**y, a continuación, haga clic en **certificados**.  
  
2.  Haga clic en el **Fabrikam cifrado** de certificados, seleccione **todas las tareas**y, a continuación, haga clic en **exportar**.  
  
3.  En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.  
  
4.  En el **exportar la clave privada** página, seleccione **No, no exportar la clave privada**y, a continuación, haga clic en **siguiente**.  
  
5.  En el **Exportar formato de archivo** página, haga clic en **siguiente**.  
  
6.  En el **archivo de exportación** página, haga clic en **examinar**.  
  
7.  En el cuadro de diálogo Guardar como, escriba  **\<unidad >: \Certs** para **guardar en**, **Encryption.cer público de Fabrikam** como **nombre de archivo**, y  **\*.cer** para **Guardar como tipo**y, a continuación, haga clic en **guardar**.  
  
8.  En el **archivo para exportar** página, haga clic en **siguiente**.  
  
9. En el **completar el Asistente para exportación de certificados** página, haga clic en **finalizar**.  
  
10. En la ventana emergente de Asistente para exportación de certificados que indica la exportación sea correcta, haga clic en **Aceptar**.  
  
11. Repita los pasos del 1 al 9 para el certificado de firma de Fabrikam mediante el nombre de archivo Signature.cer pública de Fabrikam.  
  
12. Repita los pasos del 1 al 9 para los certificados de firma de Contoso y el cifrado de Contoso con los nombres de archivo Signature.cer públicas de Contoso y Contoso Encryption.cer pública, respectivamente.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Importar Public y Private certificados](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)