---
title: 'Paso 2: Creación de certificados públicos y privados | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating certificates
- public certificates
- certificates, public certificates
- creating, certificates
- private certificates
ms.assetid: 0a925d89-03d9-41fe-907b-85a6ae42362a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f31d1bb1dcc5a0e6f587797f41e97d16ca6606da
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007613"
---
# <a name="step-2-creating-public-and-private-certificates"></a>Paso 2: Creación de certificados públicos y privados
En este paso, usará la entidad de certificación que se creó en [paso 1: creación de una entidad de certificación &#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md) para generar los certificados públicos y privados que utilizan las organizaciones de Contoso y Fabrikam.  

### <a name="to-generate-the-contoso-and-fabrikam-encryption-certificates"></a>Para generar los certificados de cifrado de Contoso y Fabrikam  

1. En el equipo que utiliza como la entidad de certificación en Internet Explorer, busque y abra http://<contoso_computername>/certsrv.  

2. En el **bienvenida** página, haga clic en **solicitar un certificado**.  

3. En el **solicitar un certificado** página, haga clic en **solicitud de certificado avanzada**.  

4. En el **solicitud de certificado avanzada** página, haga clic en **crear y enviar una solicitud a esta CA**.  

5. En el **solicitud de certificado avanzada** página, realice lo siguiente:  


   |            Use            |                                                                         Para                                                                         |
   |--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |            **Nombre**            |                                                               Tipo **Fabrikam cifrado**.                                                                |
   |           **Correo electrónico**           |                                                          Tipo <strong>jdoe@fabrikam.com</strong>.                                                          |
   |          **Compañía**           |                                                                     Tipo **Fabrikam**.                                                                     |
   |         **Departamento**         |                                                                       Tipo **prueba**.                                                                       |
   |            **Ciudad**            |                                                                       Tipo **prueba**.                                                                       |
   |           **State**            |                                                                       Tipo **prueba**.                                                                       |
   |       **País o región**       |                                                                        Tipo **US**.                                                                        |
   | **Tipo de certificado necesario** |                                             Seleccione **certificado de protección de correo electrónico** desde la lista desplegable.                                              |
   |         **Uso de claves**          |                                                              Seleccione el **Exchange** opción.                                                               |
   |   **Opciones adicionales de clave**   | Coloque una marca de verificación en las siguientes opciones:<br /><br /> -   **Marcar esta clave como exportable**<br />-   **Store certificado en el almacén de certificados equipo local** |
   |       **Nombre descriptivo**        |                                                               Tipo **Fabrikam cifrado**.                                                                |


6. Haga clic en **enviar**y, a continuación, haga clic en **Sí** en **confirmación del acceso Web** cuadro de diálogo.  

7. En el **certificado emitido** página, haga clic en **instalar este certificado**.  

8. Repita los pasos 1-7, cambiar la información de la **nombre** cuadro el **información de identificación del** sección y la **Nombre_descriptivo** cuadro a **Contoso Cifrado**.  

### <a name="to-generate-the-contoso-and-fabrikam-signing-certificates"></a>Para generar los Contoso y Fabrikam certificados de firma  

1. En Internet Explorer, busque y abra http://<contoso_computername>/certsrv.  

2. En el **bienvenida** página, haga clic en **solicitar un certificado**.  

3. En el **solicitar un certificado** página, haga clic en **solicitud de certificado avanzada**.  

4. En el **solicitud de certificado avanzada** página, haga clic en **crear y enviar una solicitud a esta CA**.  

5. En el **solicitud de certificado avanzada** página, realice lo siguiente:  


   |            Use            |                                                                         Para                                                                         |
   |--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |            **Nombre**            |                                                                Tipo **Fabrikam firma**.                                                                |
   |           **Correo electrónico**           |                                                          Tipo <strong>jdoe@fabrikam.com</strong>.                                                          |
   |          **Compañía**           |                                                                     Tipo **Fabrikam**.                                                                     |
   |         **Departamento**         |                                                                       Tipo **prueba**.                                                                       |
   |            **Ciudad**            |                                                                       Tipo **prueba**.                                                                       |
   |           **State**            |                                                                       Tipo **prueba**.                                                                       |
   |       **País o región**       |                                                                        Tipo **US**.                                                                        |
   | **Tipo de certificado necesario** |                                             Seleccione **certificado de protección de correo electrónico**.de la lista desplegable.                                              |
   |         **Uso de claves**          |                                                              Seleccione el **firma** opción.                                                              |
   |   **Opciones adicionales de clave**   | Coloque una marca de verificación en las siguientes opciones:<br /><br /> -   **Marcar esta clave como exportable**<br />-   **Store certificado en el almacén de certificados equipo local** |
   |       **Nombre descriptivo**        |                                                                Tipo **Fabrikam firma**.                                                                |


6. Haga clic en **enviar**y, a continuación, haga clic en **Sí** cuando se le pida para solicitar el certificado.  

7. En el **certificado emitido** página, haga clic en **instalar este certificado**.  

8. Repita los pasos 1-7, cambiar la información de la **nombre** cuadro el **información de identificación del** sección y la **Nombre_descriptivo** cuadro a **Contoso Firma**.  

### <a name="to-generate-private-certificates-for-the-encryption-and-signature-certificates"></a>Para generar certificados privados para los certificados de cifrado y firma  

1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **MMC**y, a continuación, haga clic en **Aceptar**.  

2.  En la ventana Consola1, en el **archivo** menú, haga clic en **agregar o quitar complemento**.  

3.  En el cuadro de diálogo Agregar o quitar complemento, en el **independiente** , haga clic **agregar**.  

4.  En el cuadro de diálogo Add Standalone Snap-in, seleccione el **certificados** complemento desde la **complementos Standalone disponibles** lista y, a continuación, haga clic en **agregar**.  

5.  En el cuadro de diálogo complemento de certificados, seleccione **mi cuenta de usuario**y, a continuación, haga clic en **siguiente**.  

6.  En el cuadro de diálogo Seleccionar equipo, haga clic en **finalizar**.  

7.  En el cuadro de diálogo Add Standalone Snap-in, haga clic en **cerrar**.  

8.  En el cuadro de diálogo Agregar o quitar complemento, haga clic en **Aceptar**.  

9. En la ventana Consola1, expanda **certificados (equipo Local)**, expanda **Personal**y, a continuación, haga clic en **certificados**.  

10. En el panel derecho, haga clic en el **Fabrikam cifrado** de certificado, seleccione **todas las tareas**y, a continuación, haga clic en **exportar**.  

11. En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.  

12. En el **exportar la clave privada** página, seleccione **Sí, exportar la clave privada**y, a continuación, haga clic en **siguiente**.  

13. En el **Exportar formato de archivo** página, asegúrese de que **Personal Information Exchange** es la única opción seleccionada y, a continuación, haga clic en **siguiente**.  

14. En el **contraseña** página, en el **contraseña** y **Confirmar contraseña** cuadros, escriba **MiSecreto**y, a continuación, haga clic en **siguiente** .  

15. En el **archivo de exportación** página, haga clic en **examinar**.  

16. En el **Guardar como** cuadro de diálogo, guarde el certificado con la ruta de acceso de archivo  *\<unidad\>*: \Certs\Fabrikam Encryption.pfx privada.  

17. En el **archivo para exportar** página, haga clic en **siguiente**.  

18. En el **completar el Asistente para exportar certificados** página, haga clic en **finalizar**.  

19. En el menú emergente de Asistente para exportar certificados que indica una exportación correcta, haga clic en **Aceptar**.  

20. Repita los pasos 10-19 para el certificado de firma de Fabrikam mediante el nombre de archivo Signature.pfx privada de Fabrikam.  

21. Repita los pasos 10-19 para los certificados de firma de Contoso y el cifrado de Contoso mediante los nombres de archivo Signature.pfx privado de Contoso y Encryption.pfx privado de Contoso, respectivamente.  

### <a name="to-generate-public-certificates-for-the-encryption-and-signature-certificates"></a>Para generar certificados públicos para los certificados de cifrado y firma  

1.  En la ventana Consola1, expanda **certificados – usuario actual**, expanda **Personal**y, a continuación, haga clic en **certificados**.  

2.  Haga clic en el **Fabrikam cifrado** de certificado, seleccione **todas las tareas**y, a continuación, haga clic en **exportar**.  

3.  En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.  

4.  En el **exportar la clave privada** página, seleccione **No, no exportar la clave privada**y, a continuación, haga clic en **siguiente**.  

5.  En el **Exportar formato de archivo** página, haga clic en **siguiente**.  

6.  En el **archivo de exportación** página, haga clic en **examinar**.  

7.  En el cuadro de diálogo Guardar como, escriba  **\<unidad\>: \Certs** para **guardar en**, **Fabrikam pública Encryption.cer** como **nombre de archivo** , y  **\*.cer** para **Guardar como tipo**y, a continuación, haga clic en **guardar**.  

8.  En el **archivo para exportar** página, haga clic en **siguiente**.  

9. En el **completar el Asistente para exportar certificados** página, haga clic en **finalizar**.  

10. En el menú emergente de Asistente para exportar certificados que indica una exportación correcta, haga clic en **Aceptar**.  

11. Repita los pasos 1 a 9 para el certificado de firma de Fabrikam mediante el nombre de archivo Signature.cer pública de Fabrikam.  

12. Repita los pasos 1 a 9 para los certificados de firma de Contoso y el cifrado de Contoso mediante los nombres de archivo Signature.cer público de Contoso y Encryption.cer público de Contoso, respectivamente.  

## <a name="see-also"></a>Vea también  
 [Paso 3: Importar certificados públicos y privados](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)