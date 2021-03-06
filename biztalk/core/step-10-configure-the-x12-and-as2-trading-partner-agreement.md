---
title: 'Paso 10: Configurar el acuerdo de socio X12 y comerciales de AS2 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8fcdb3af-727a-4d20-9dcf-cf162e7d3398
caps.latest.revision: 46
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beae325fa0a0cfcc2c4a63f3134ccb39e5e243d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996045"
---
# <a name="step-10-configure-the-x12-and-as2-trading-partner-agreement"></a>Paso 10: Configurar el acuerdo de socio X12 y comerciales de AS2
![Paso 10 de 11](../core/media/tut-step10-of-11.gif "Tut_Step10_of_11")  

 En este paso, configurará acuerdos de socios comerciales de X12 y AS2 para transportar un mensaje codificado en EDIINT/AS2 a través de HTTP. Esta entidad de Fabrikam envía el intercambio EDI a Contoso, que devuelve la confirmación 997 y un MDN asincrónico a Fabrikam.  

## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

### <a name="to-create-an-as2-agreement"></a>Procedimiento para crear un acuerdo AS2  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **partes** en el árbol de consola y, en el **entidades y perfiles empresariales** página, haga clic en **Fabrikam_Profile**, apunte a **New**y, a continuación, haga clic en **contrato**.  

3. En el **propiedades generales** página, para el **nombre** texto, escriba un nombre para el acuerdo.  

4. Desde el **protocolo** lista desplegable, seleccione **AS2**.  

5. En el **segundo socio** sección, desde el **nombre** lista desplegable, seleccione **Contoso**.  

6. En el **segundo socio** sección, desde el **perfil** lista desplegable, seleccione **Contoso_Profile**.  

    Observará que las dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha sirve para configurar un acuerdo AS2 unidireccional.  

7. En el **General** ficha la **propiedades generales** página, en el **configuración de Host común** sección, seleccione **activar informes**.  

8. Realizar las tareas siguientes en el **Fabrikam -> Contoso** ficha.  

   1.  En el **identificadores** , escriba valores para **AS2-desde** y **AS2-para**. Para **AS2-desde**, escriba `Fabrikam`. Para **AS2 - To**, escriba `Contoso`.  

   2.  En el **validación** página, seleccione el **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** casilla de verificación  

       > [!NOTE]
       >  Si se establece esta propiedad, se asegura que se usarán las propiedades de la entidad al generar el MDN, en lugar de los encabezados de AS2 del mensaje AS2 recibido.  

   3.  En el **confirmaciones (MDN)** página, realice lo siguiente:  

       1.  Seleccione el **solicitar MDN** casilla de verificación.  

       2.  Asegúrese de que el **solicitar MDN firmado** casilla está desactivada.  

       3.  Seleccione el **solicitar MDN asíncrono** casilla de verificación.  

       4.  En el **Receipt-Delivery-Option (URL)** texto, escriba `http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`.  

9. Realizar las tareas siguientes en el **Contoso -> Fabrikam** ficha.  

   1. En el **identificadores** , escriba valores para **AS2-desde** y **AS2-para**. Para **AS2-desde**, escriba `Contoso`. Para **AS2 - To**, escriba `Fabrikam`.  

   2. En el **puertos de envío** página bajo la **configuración de intercambio** sección la **puertos de envío** lista, para **nombre** seleccione  **Send_Async_997**.  

      > [!NOTE]
      >  El puerto de envío Send_Async_997 debe especificarse en el **puertos de envío** lista para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueda resolver la entidad para el mensaje 997 saliente. La canalización de envío coincide con el nombre del puerto de envío de las propiedades del acuerdo. Esto es necesario porque, en este caso, la propiedad AS2-To no se promociona en el contexto del mensaje, que es la primera correspondencia que intenta realizar la canalización de envío para resolver la entidad. Para obtener más información, consulte [resolución del acuerdo para mensajes AS2 salientes](../core/agreement-resolution-for-outgoing-as2-messages.md).  

10. Haga clic en **Aplicar**.  

11. Haga clic en **Aceptar**. El acuerdo recién agregado aparece en la **acuerdos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  

### <a name="to-create-an-x12-agreement"></a>Procedimiento para crear un acuerdo X12  

1. Haga clic en **Fabrikam_Profile**, apunte a **New**y, a continuación, haga clic en **contrato**.  

2. En el **propiedades generales** página, para el **nombre** texto, escriba un nombre para el acuerdo.  

3. Desde el **protocolo** lista desplegable, seleccione **X12**.  

4. En el **segundo socio** sección, desde el **nombre** lista desplegable, seleccione **Contoso**.  

5. En el **segundo socio** sección, desde el **perfil** lista desplegable, seleccione **Contoso_Profile**.  

    Observará que las dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha sirve para configurar un acuerdo X12 unidireccional.  

6. En el **General** ficha la **propiedades generales** página, en el **configuración de Host común** sección, seleccione **activar informes**y, a continuación, Seleccione **carga de mensaje de Store para el informe**.  

7. Realizar las tareas siguientes en el **Fabrikam -> Contoso** ficha.  

   1. En el **identificadores** página bajo la **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba. Para este tutorial, establezca **ISA5** a **ZZ**, **ISA6** a **7654321**, **ISA7** a **ZZ** , y **ISA8** a **1234567**.  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesita los campos de identificador y calificador del remitente y del receptor para realizar una resolución de acuerdo. Lo hará coincidir los valores de **ISA5**, **ISA6**, **ISA7**, y **ISA8** en el encabezado del intercambio con aquellos de las propiedades de un acuerdo. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] también resolverá el acuerdo haciendo coincidir el calificador de remitente y el identificador (sin el calificador e identificador). Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede resolver el acuerdo, usará las propiedades de acuerdo de reserva.  

   2. En el **confirmaciones** página bajo la **configuración de intercambio** sección, seleccione el **997 esperado** casilla de verificación.  

   3. En el **validación** página bajo la **configuración de intercambio** sección, asegúrese de que **comprobación de duplicado ISA13** opción está desactivada.  

      > [!NOTE]
      >  Borrar el **comprobación de duplicado ISA13** propiedad le permite recibir varias instancias del mismo mensaje.  

   4. En el **configuración de Host Local** página bajo el **configuración de intercambio** en sección **configuración del receptor**, desactive **enrutar confirmación para enviar una canalización puerto de recepción de solicitud-respuesta**.  

      > [!NOTE]
      >  Si se desactiva esta propiedad, podrá enviar la confirmación 997 a través de un puerto de envío independiente en lugar de enviarlo a través del puerto de envío asociado con el puerto de recepción bidireccional.  

8. Realizar las tareas siguientes en el **Contoso -> Fabrikam** ficha.  

   1. En el **identificadores** página bajo la **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  En este tutorial, establezca **ISA5** a **ZZ**, **ISA6** a **1234567**, **ISA7** a **ZZ** , y **ISA8** a **7654321**.  

   2. En el **juego de caracteres y separadores** página bajo la **configuración de intercambio** sección, para **sufijo**, seleccione **CR LF**.  

   3. En el **sobres** página bajo la **configuración del conjunto de transacciones** sección, realice lo siguiente:  


      |       Use       |                                                                                                                                              Para                                                                                                                                               |
      |----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     **Default**      |              Seleccione **predeterminado**. **Nota:** al seleccionar esta fila de forma predeterminada, los valores de **GS1**, **GS2**, **GS3**, **GS7**, y  **GS8** se usan incluso si los valores de **tipo de transacción**, **versión**, y **espacio de nombres de destino** no son una coincidencia para el mensaje.              |
      | **Tipo de transacción** |                                                                                                          Seleccione el tipo de mensaje del mensaje de prueba, por ejemplo, **864 – Text Message**.                                                                                                           |
      | **Versión y lanzamiento**  |                                                                                                                                           Escriba **00401**.                                                                                                                                            |
      | **Espacio de nombres de destino** |                                                                                                                    Seleccione **<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>**.                                                                                                                    |
      |       **GS1**        |                                                                                                Compruebe que está seleccionado el tipo de mensaje del mensaje de prueba, por ejemplo, **TX - Text Message (864)**.                                                                                                |
      |       **GS2**        |                                                                                                                                             Escriba **01**.                                                                                                                                             |
      |       **GS3**        |                                                                                                                                          Escriba **7654321**.                                                                                                                                           |
      |       **GS4**        | Seleccionar el formato de fecha que desee. Seleccione **SSAAMMDD**. **Nota:** tiene que seleccionar el valor en la lista desplegable, haga clic en no solo en el campo para mostrar el valor predeterminado. Si hace clic en el campo sin seleccionar el valor de la lista desplegable, el valor no se seleccionará realmente. |
      |       **GS5**        |                                                                                                                      Seleccione el formato de hora que desee. Seleccione **HHMMSSdd**.                                                                                                                       |
      |       **GS7**        |                                                                                                                   Seleccione **T - Transportation Data Coordinating Committee (TDCC)**.                                                                                                                   |
      |       **GS8**        |                                                                                                                      Compruebe que la versión de EDI se ha especificado como **00401**.                                                                                                                       |


9. Haga clic en **Aplicar**.  

10. Haga clic en **Aceptar**. El acuerdo recién agregado aparece en la **acuerdos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  

11. Reinicie el servicio de BizTalk. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en **configuración de plataforma**, haga clic en **instancias de Host**, haga clic en **BizTalkServerApplication**y, a continuación, haga clic en  **Reinicie**.  

## <a name="next-steps"></a>Pasos siguientes  
 Probar la solución AS2, como se describe en [paso 11: probar la solución AS2](../core/step-11-test-the-as2-solution.md).  

## <a name="see-also"></a>Vea también  
 [Configurar propiedades de AS2](../core/configuring-as2-properties.md)   
 [Configuración de las propiedades de EDI](../core/configuring-edi-properties.md)