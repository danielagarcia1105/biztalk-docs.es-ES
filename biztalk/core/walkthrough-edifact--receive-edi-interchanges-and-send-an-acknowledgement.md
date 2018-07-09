---
title: 'Tutorial (EDIFACT): Recepción de intercambios EDI y devolver una confirmación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02751f0c-8e7e-4879-93e4-8bc475640756
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b221d47a64f603db697b99c7e5a60b1cb1a67bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018894"
---
# <a name="walkthrough-edifact-receiving-edi-interchanges-and-sending-back-an-acknowledgement"></a>Tutorial (EDIFACT): Recepción de intercambios EDI y devolución de una confirmación
Este tutorial proporciona un conjunto de procedimientos descritos paso a paso que crean una solución para recibir intercambios de EDIFACT mediante el uso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En esta solución, se envía un intercambio EDIFACT desde un socio comercial, Fabrikam, a otro, Contoso.  

## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

## <a name="how-the-solution-receives-edifact-interchanges"></a>Cómo la solución recibe intercambios EDIFACT  
 La solución hará lo siguiente:  

> [!NOTE]
>  Puede que los eventos de esta lista no se produzcan en el orden mostrado.  

1.  Recibir un intercambio EDIFACT de archivos sin formato del socio comercial Fabrikam.  

2.  Validar el intercambio EDIFACT con su esquema, desensamblar el mensaje a XML y depositar el mensaje XML en el cuadro de mensajes.  

3.  Generar una confirmación TÉCNICA (recepción de mensaje) al intercambio EDI recibido y depositarla en el cuadro de mensajes.  

4.  Generar una confirmación funcional (aceptación o rechazo del intercambio EDI recibido) y depositarla en el cuadro de mensajes.  

5.  Recoger el mensaje XML mediante un puerto de envío de ARCHIVOS unidireccional y ensamblar el intercambio EDI.  

6.  Enviar un intercambio EDI a la carpeta local de Contoso.  

7.  Recoger la confirmación técnica mediante un puerto de envío de ARCHIVOS unidireccional y ensamblar el intercambio.  

8.  Enviar la confirmación técnica a la carpeta local de Fabrikam.  

9. Recoger la confirmación funcional mediante un puerto de envío de ARCHIVOS unidireccional y ensamblar el intercambio.  

10. Enviar la confirmación funcional a Fabrikam.  

## <a name="the-functionality-in-this-solution"></a>La funcionalidad en esta solución  
 Por lo que respecta a este tutorial, se habilitará la siguiente funcionalidad:  

- La solución está diseñada para intercambios que usan la codificación EDIFACT  

  > [!NOTE]
  >  Para obtener instrucciones sobre cómo crear una solución similar para intercambios X12, consulte [tutorial (X12): devolución de una confirmación de envío y recepción de intercambios EDI](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md).  

- El tipo de codificación EDI y la validación extendida se realizarán en el intercambio entrante.  

- Se generarán confirmaciones técnicas y funcionales para la devolución del intercambio al remitente.  

- La solución usa una ubicación de recepción unidireccional con un tipo de transporte de archivo.  

  > [!NOTE]
  >  Puede usar un puerto de recepción bidireccional de petición-respuesta y una ubicación para recibir el mensaje; no obstante, si lo hace, no podrá usar un tipo de transporte de archivo para la ubicación de recepción. Para obtener más información, consulte [configurar un puerto para recibir mensajes de EDI y confirmaciones](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md).  

- Se habilitarán los informes EDI y se guardarán los conjuntos de transacciones para su visualización a partir del informe de estado de intercambio.  

- Para realizar pruebas, la solución usa tres puertos de envío para enviar el intercambio EDIFACT y las confirmaciones creadas a carpetas locales.  

  La siguiente ilustración muestra la arquitectura de esta solución:  

  ![Recepción de intercambio EDIFACT y envío de confirmación](../core/media/edifact-walkthrough.gif "EDIFACT_Walkthrough")  

## <a name="configuring-and-testing-the-walkthrough"></a>Configuración y prueba del tutorial  
 Los procedimientos necesarios para esta solución son:  

- Agregue los esquemas de mensaje necesarios a un proyecto de BizTalk y, a continuación, genere e implemente el proyecto, de modo que los esquemas estén disponibles para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los use a la hora de procesar el intercambio recibido.  

- Crear un puerto de recepción unidireccional para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reciba el intercambio EDIFACT del socio comercial y genere una confirmación. La ubicación de recepción está vinculada a la carpeta de archivo donde Fabrikam suelta el intercambio EDIFACT que debe enviarse a Contoso.  

  > [!NOTE]
  >  Puede usar el puerto de recepción de solicitud-respuesta y la ubicación para recibir el mensaje de petición-respuesta bidireccional, pero si lo hace, no podrá usar un tipo de transporte de archivo para la ubicación de recepción.  

- Cree un puerto de envío que envíe el intercambio EDI a una carpeta local de Contoso y otro que envíe las confirmaciones técnica y funcional a una carpeta local de Fabrikam.  

  > [!NOTE]
  >  A diferencia de las confirmaciones X12, los tipos de mensajes para las confirmaciones tanto funcionales como técnicas son los mismos. Por tanto, el filtro del puerto de envío creado mediante la propiedad de contexto de `BTS.MessageType` filtra ambas confirmaciones y las entrega a la misma carpeta.  

- Crear una entidad (socio comercial) para Fabrikam y Contoso.  

- Crear un perfil de negocio para cada uno de los socios comerciales.  

- Cree un acuerdo entre los dos perfiles configurando las propiedades EDI para el mensaje que se va a recibir y la confirmación que se va a enviar.  

- Pruebe el tutorial con un intercambio de prueba EDIFACT. Para este tutorial, puede copiar y pegar lo siguiente en un archivo de texto. El esquema para este archivo es EFACT_D98A_APERAK.xld.  

  ```  
  UNA:+,?*'  
  UNB+UNOB:1+7654321:ZZZ+1234567:ZZZ+353501:3023+UNB5'  
  UNG+INVOIC+UNG2.1:ZZZ+UNG3.1:ZZZ+060413:2314+UNG5+UN+D:98B'  
  UNH+UNH1+APERAK:D:98A:UN++13+UNH5.1+UNH6.1+UNH7.1'  
  BGM+1+C10601'  
  DTM+10'  
  FTX+AAA++C10701+C10801'  
  CNT+1:14'  
  RFF+AAA'  
  DTM+10'  
  NAD+AA+C08201+C05801+C08001+C05901'  
  CTA++C05601'  
  COM+C07601:AA'  
  ERC+C90101'  
  FTX+AAA++C10701+C10801'  
  RFF+AAA'  
  FTX+AAA++C10701+C10801'  
  UNT+15+UNH1'  
  UNE+1+UNG5'  
  UNZ+1+UNB5'  
  ```  

### <a name="configuring-the-walkthrough"></a>Configuración del tutorial  
 En esta sección se describen los procedimientos para configurar el tutorial.  

##### <a name="to-deploy-the-message-schema"></a>Para implementar el esquema de mensajes  

1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree o abra un proyecto de BizTalk.  

   > [!NOTE]
   >  Este tema presupone que ya ha agregado una referencia de su aplicación a la aplicación EDI de BizTalk, que contiene esquemas, canalizaciones y orquestaciones EDI. Si no, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  

2. Haga clic en el proyecto, elija **agregar**y, a continuación, haga clic en **elemento existente**. Desplácese a la carpeta donde está el esquema en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A y, a continuación, haga doble clic en el esquema (**EFACT_D98A_APERAK.xsd**).  

   > [!NOTE]
   >  Si está utilizando el mensaje de prueba de ejemplo proporcionado en este tema, debe usar el **EFACT_D98A_APERAK.xsd** esquema.  

   > [!NOTE]
   >  Si los esquemas EDI no se han descomprimido en las carpetas \XSD_Schema\EDI, ejecute el **MicrosoftEdiXSDTemplates.exe** archivo en la carpeta \XSD_Schema\EDI para descomprimir los esquemas en la carpeta predeterminada.  

3. Agregue el archivo de clave de ensamblado en el proyecto y, a continuación, genere e implemente el ensamblado.  

##### <a name="to-create-a-one-way-receive-port-for-fabrikam-to-receive-the-edi-interchange"></a>Procedimiento para crear un puerto de recepción unidireccional (para Fabrikam) para recibir el intercambio EDI  

1. En el Explorador de Windows, cree una carpeta local en la que recibir el intercambio.  

2. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de recepción** nodo bajo el **BizTalk Application 1** nodo, seleccione **New**y, a continuación, haga clic en **Unidireccional puerto de recepción**.  

3. Nombre del puerto de recepción y, a continuación, haga clic en **ubicaciones de recepción** en el árbol de consola.  

4. Haga clic en **Nueva**.  

5. Nombre de la ubicación de recepción, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  

6. Busque una carpeta para **carpeta recepción** cuadro de texto. Esta carpeta la creó en el paso 1 de este procedimiento. Escriba una máscara de archivo, como  **\*.edi** o  **\*.txt**.  

7. Haga clic en **Aceptar**.  

8. Para **canalización de recepción**, seleccione **EdiReceive**.  

9. Haga clic en **Aceptar** en el **propiedades de ubicación de recepción** cuadro de diálogo. Haga clic en **Aceptar** nuevo en el **propiedades de puerto de recepción** cuadro de diálogo.  

10. En el árbol de consola, haga clic en **ubicaciones de recepción**. En el **ubicaciones de recepción** panel, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**.  

##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a>Procedimiento para crear un puerto de envío estático unidireccional (para Contoso) para enviar el intercambio EDI  

1. En el Explorador de Windows, cree una carpeta local a la que enviar el intercambio de prueba.  

2. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de envío** nodo bajo el **BizTalk Application 1** nodo, seleccione **New**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  

3. En el **propiedades de puerto de envío** cuadro de diálogo, nombre el puerto de envío.  

4. En el **transporte** sección, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  

5. Para **carpeta de destino**, vaya a la carpeta para recibir el intercambio. Esta carpeta la creó en el paso 1 de este procedimiento. Para **máscara de archivo**, especifique el formato de intercambio, como  **\*.edi** o  **\*.txt**.  

6. Haga clic en **Aceptar**.  

7. En **canalización de envío**, seleccione **EdiSend**.  

8. En el árbol de consola, seleccione **filtros**. Especifique un filtro al que suscribir el intercambio EDI. Por ejemplo, para **propiedad**, escriba **BTS. MessageType**; para **operador**, escriba **==**; y para **valor** especifique el esquema para el intercambio, `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006#EFACT_D98A_APERAK`.  

   > [!NOTE]
   >  La configuración de filtro anterior asegura que esos intercambios, no las confirmaciones, se enviarán a la carpeta asociada a este puerto de envío.  

9. Haga clic en **Aceptar**.  

10. En el árbol de consola, haga clic en **puertos de envío**. En el **puertos de envío** panel, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  

##### <a name="to-create-a-static-one-way-send-port-to-send-the-acknowledgments"></a>Procedimiento para crear un puerto de envío estático unidireccional para enviar las confirmaciones  

1. En el Explorador de Windows, cree una carpeta local a la que enviar las confirmaciones técnica y funcional.  

2. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de envío** nodo bajo el **BizTalk Application 1** nodo, seleccione **New**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  

3. En el **propiedades de puerto de envío** cuadro de diálogo, nombre el puerto de envío.  

4. En el **transporte** sección, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  

5. Para **carpeta de destino**, busque una carpeta para recibir las dos confirmaciones. Esta carpeta la creó en el paso 1 de este procedimiento. Para **máscara de archivo**, especifique el formato de intercambio, como  **\*.edi** o  **\*.txt**.  

6. Haga clic en **Aceptar**.  

7. En **canalización de envío**, seleccione **EdiSend**.  

8. En el árbol de consola, seleccione **filtros**. Especifique un filtro al que suscribir las confirmaciones. Por ejemplo, para **propiedad**, escriba **BTS. MessageType**; para **operador**, escriba **==**; y para **valor** especifique el esquema para la confirmación, `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`.  

9. Haga clic en **Aceptar**.  

10. En el árbol de consola, haga clic en **puertos de envío**. En el **puertos de envío** panel, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  

##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a>Para crear una entidad y un perfil de negocio para Fabrikam  

1. Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  

2. Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  

   > [!NOTE]
   >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite las partes o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es para la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  

3. Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  

4. En el **propiedades de perfil** cuadro de diálogo el **General** , escriba **Fabrikam_Profile** en el **nombre** cuadro de texto.  

   > [!NOTE]
   >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** , especifique un nombre para el perfil.  

##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a>Para crear una entidad y un perfil de negocio para Contoso  

1. Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  

2. Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  

   > [!NOTE]
   >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite las partes o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es para la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  

3. Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  

4. En el **propiedades de perfil** cuadro de diálogo el **General** , escriba **Contoso_Profile** en el **nombre** cuadro de texto.  

   > [!NOTE]
   >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** , especifique un nombre para el perfil.  

##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a>Para crear un acuerdo entre los dos perfiles de negocio  

1. Haga clic en **Fabrikam_Profile**, apunte a **New**y, a continuación, haga clic en **contrato**.  

2. En el **propiedades generales** página, para el **nombre** texto, escriba un nombre para el acuerdo.  

3. Desde el **protocolo** lista desplegable, seleccione **EDIFACT**.  

4. En el **segundo socio** sección, desde el **nombre** lista desplegable, seleccione **Contoso**.  

5. En el **segundo socio** sección, desde el **perfil** lista desplegable, seleccione **Contoso_Profile**.  

    Observará que las dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha es para configurar un acuerdo unidireccional y cada acuerdo unidireccional representa una transacción completa del mensaje (incluida la transferencia del mensaje y la transferencia de la confirmación).  

6. En el **General** ficha la **propiedades generales** página, en el **configuración de Host común** sección, seleccione **activar informes**y, a continuación, Seleccione **carga de mensaje de Store para el informe**.  

7. Realizar las tareas siguientes en el **Fabrikam -> Contoso** ficha.  

   1. En el **identificadores** página bajo la **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**UNB2.1**, **UNB2.2**, **UNB3.1**, y **UNB3.2**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesita los campos de identificador y calificador del remitente y del receptor para realizar una resolución de acuerdo. Lo hará coincidir los valores de **UNB2.1**, **UNB2.2**, **UNB3.1**, y **UNB3.2** en el encabezado del intercambio con aquellos de las propiedades de un contrato. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] también resolverá el acuerdo haciendo coincidir el calificador de remitente y el identificador (sin el calificador e identificador). Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede resolver el acuerdo, usará las propiedades de acuerdo de reserva.  
      > 
      > [!NOTE]
      >  Si está utilizando el mensaje de ejemplo proporcionado anteriormente en este tema como mensaje de prueba, establecer **UNB2.1** a **7654321**, **UNB2.2** a **ZZZ – definidos mutuamente** , **UNB3.1** a **1234567**, y **UNB3.2** a **ZZZ – definido mutuamente**.  

   2. En el **confirmaciones** página bajo el **configuración de intercambio** sección, verificación **recepción del mensaje (CONTRL) esperada** y **(confirmación CONTRL) esperada**.  

   3. En el **sobres** página bajo el **configuración de intercambio** sección, verificación **aplicar segmento UNA (notificación del servicio)** y **UNG aplicar segmentos () Encabezado de grupo funcional)**.  

   4. En el **validación** página bajo la **configuración de intercambio** sección, asegúrese de que **número de Control de intercambio (UNB5)** opción está desactivada.  

      > [!NOTE]
      >  Borrar el **número de Control de intercambio (UNB5)** propiedad le permite recibir varias instancias del mismo mensaje.  

   5. En el **juego de caracteres y separadores** página bajo la **configuración de intercambio** sección, seleccione el **CR LF** opción **sufijo UNA6**.  

   6. En el **configuración de Host Local** página bajo la **configuración de intercambio** sección, desactive la **enrutar confirmación para la canalización de envío de solicitud-respuesta de puerto de recepción** opción.  

      > [!NOTE]
      >  Si usaba puerto para recibir el intercambio y devolver la confirmación de recepción bidireccional, se comprobaría si **enrutar confirmación para la canalización de envío de solicitud-respuesta de puerto de recepción**.  

   7. En el **puertos de envío** página bajo la **la configuración de intercambio** sección, asocie los puertos de envío que va a recibir el intercambio de Fabrikam y los puertos de envío que va a recibir el confirmaciones de Contoso. En el **puertos de envío** cuadrícula, en el **nombre** columna, haga clic en una celda vacía y, en la lista desplegable, seleccione el puerto de envío creado para recibir el intercambio EDI de Fabrikam. Repita el paso del puerto de envío creado para recibir las confirmaciones técnica y funcional.  

   8. En el **validación** página bajo la **configuración del conjunto de transacciones** deje **validación de tipo EDI** activada y comprobar **validación de tipo extendido**.  

   9. Si está usando uno de los esquemas estándar incluidos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], en el **configuración de Host Local** página bajo la **configuración del conjunto de transacciones** , seleccione el espacio de nombres del esquema que se va a usarse para procesar el intercambio entrante. Si usa un esquema personalizado, especifique valores en el **personalizar Target namespace de** cuadrícula, por lo que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede determinar el espacio de nombres utilizando transacciones de grupo y establece los valores de encabezado.  

   10. En el **sobres** página bajo la **configuración del conjunto de transacciones** sección, especifique valores para todas las columnas de la primera línea de la cuadrícula.  


       |          Use           |                                Para                                 |
       |-----------------------------|---------------------------------------------------------------------------|
       |         **Default**         |                            Seleccione **predeterminado**.                            |
       | **Para el tipo de mensaje UNH2.1** |         Seleccione el tipo de mensaje del mensaje de prueba, **APERAK**.         |
       |         **UNH2.2**          |                       Especifique la versión EDI, **d.**.                       |
       |         **UNH2.3**          |                    Escriba el número de versión, **98A**.                     |
       |         **UNH2.5**          |                         Puede dejarlo en blanco.                         |
       |    **Espacio de nombres de destino**     |          Seleccione **<http://schemas.microsoft.com/Edi/Edifact>**.           |
       |          **UNG1**           |               Especifique el identificador de grupo funcional, **INVOIC**.                |
       |         **UNG2.1**          |         Escriba un valor para la identificación del remitente de la aplicación.          |
       |         **UNG2.1**          | Escriba un valor para el calificador de código de remitente de aplicación, como **ZZZ**. |
       |         **UNG3.1**          |          Introduzca un valor para la identificación del receptor de la aplicación.           |
       |         **UNG3.2**          |  Escriba un valor para el calificador del código de receptor de aplicación, como **ZZZ**.  |
       |          **UNG6**           |        Escriba un valor para la Agencia de control. Ejemplo, **anular**.         |
       |         **UNG7.1**          |          Escriba el número de versión del tipo de mensaje. Ejemplo, **d.**.           |
       |         **UNG7.2**          |         Escriba el número de lanzamiento del tipo de mensaje. Ejemplo, **98A**.          |
       |         **UNG7.3**          |                         Puede dejarlo en blanco.                         |
       |          **UNG8**           |                         Puede dejarlo en blanco.                         |


8. Realizar las tareas siguientes en el **Contoso -> Fabrikam** ficha.  

   > [!NOTE]
   >  En este tutorial, especificamos el valor necesario en la ficha para que se pueda crear un acuerdo correctamente. Para crear correctamente un acuerdo, ambas fichas de acuerdo unidireccional deben tener valores definidos para **UNG2.1**, **UNG2.2**, **UNG3.1**, y **UNG3.2**.  

   > [!NOTE]
   >  Aunque la confirmación es parte de la misma transacción de mensaje, se configuran las propiedades relacionadas con el modo en que debe generarse la confirmación en el **Contoso -> Fabrikam** ficha. Esto es necesario porque las propiedades de contexto de confirmación para el remitente y receptor calificadores se establecen en el efecto contrario de los valores especificados en el **Contoso -> Fabrikam** ficha. Por ejemplo, si remitente y receptor se establecen los identificadores en 7654321 y 1234567 en la **Fabrikam -> Contoso** propiedades de contexto de la ficha, el remitente y receptor se establecerá en 1234567 y 7654321 en la confirmación. Normalmente, la otra pestaña de acuerdo unidireccional también tendrá los identificadores de remitente y receptor configurados respectivamente en 1234567 y 7654321. Por lo tanto, el mensaje de confirmación se resolverá en dicho acuerdo y se seleccionará la configuración de propiedades. Por lo tanto, si desea tener confirmación para usar diferentes separadores de elementos o si desea tener confirmación para usar CR LF, especifique las propiedades en el **Contoso -> Fabrikam** ficha.  
   >   
   >  Conceptualmente, las propiedades para la confirmación se seleccionarán desde cualquier ficha de acuerdo unidireccional que tenga los mismos calificadores de remitente y receptor que están configurados en las propiedades de contexto de la confirmación. No obstante, para facilitar su uso en la práctica, normalmente debe configurar esto en la otra ficha de acuerdo unidireccional del acuerdo que creó en el cual debe haberse resuelto el intercambio.  

   1.  En el **identificadores** página bajo la **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**UNG2.1**, **UNG2.2**, **UNG3.1**, y **UNG3.2**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  

       > [!NOTE]
       >  Si está utilizando el mensaje de ejemplo proporcionado anteriormente en este tema como mensaje de prueba, establecer **UNB2.1** a **1234567**, **UNB2.2** a **ZZZ – definidos mutuamente** , **UNB3.1** a **7654321**, y **UNB3.2** a **ZZZ – definido mutuamente**.  

9. Haga clic en **Aplicar**.  

10. Haga clic en **Aceptar**. El acuerdo recién agregado aparece en la **acuerdos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  

### <a name="testing-the-walkthrough"></a>Probar el tutorial  
 Esta sección proporciona información acerca de cómo probar el tutorial.  

##### <a name="to-test-the-walkthrough"></a>Para probar el tutorial  

1. En el Explorador de Windows, coloque el intercambio EDI de prueba en su carpeta de recepción local.  

   > [!NOTE]
   >  Para un mensaje de prueba, puede usar el mensaje de ejemplo proporcionada anteriormente en este tema. Copie el mensaje a un archivo de texto y guarde el archivo con una extensión .txt. Si usa este mensaje, debe haber implementado el esquema EFACT_D98A_APERAK.xsd. El esquema está disponible mediante la ejecución de la **MicrosoftEdiXSDTemplates.exe** archivo (en la carpeta \XSD_Schema\EDI) para descomprimir los esquemas en la carpeta predeterminada. El esquema EFACT_D98A_APERAK.xsd estará entonces disponible bajo [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A.  

2. Abra la carpeta asociada al puerto de envío para los intercambios y compruebe que ésta contiene el intercambio EDI.  

3. Abra la carpeta asociada al puerto de envío para las confirmaciones y compruebe que ésta contiene las confirmaciones técnica y funcional.  

## <a name="see-also"></a>Vea también  
 [Desarrollo y configuración de soluciones EDI de BizTalk Server](../core/developing-and-configuring-biztalk-server-edi-solutions.md)