---
title: 'Paso 1: Enviar solicitud un 0c 2 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 698c4a43-20b9-46b7-ab66-1dfa24232024
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f05aa5200bd1df6207a962849cd776a03fe71805
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-submitting-a-0c2-request"></a>Paso 1: Enviar un 0c solicitar 2
En este paso, se preparará y enviará una solicitud con el proceso de interfaz de socio (PIP) para un 0c 2 - solicitud asincrónica de prueba. Este PIP garantiza que un canal de comunicación asincrónica funciona correctamente entre dos organizaciones diferentes. Este PIP sigue el mismo patrón que otros PIP de doble acción asincrónica, como el 3A4 - solicitud PIP de pedido de compra.  
  
### <a name="to-submit-a-0c2---asynchronous-test-request"></a>Para enviar un 0c 2 - solicitud asincrónica de prueba  
  
1.  En el equipo de Fabrikam, en Internet Explorer, busque y abra http://localhost/LOBWebApplication/default.aspx.  
  
2.  En la página **Enviar mensaje** , haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Organización principal**|Escriba **FABRIKAM**.|  
    |**Organización de socios comerciales**|Escriba **CONTOSO**.|  
    |**Código PIP**|Tipo de **0c2**.|  
    |**Versión de PIP**|Escriba **R01.02**.|  
    |**Id. de instancia de PIP**|Tipo de **0C2_Test**. **Importante:** debe asegurarse de que el **PIP** es único para cada mensaje que se envía para evitar errores de Id. de mensaje duplicado. Si ejecuta el 0 C 2 probar en el futuro, tendrá que cambiar este campo.|  
    |**Categoría de mensaje**|Escriba **Acción**.|  
  
3.  Con el Bloc de notas u otro editor de texto, abra el archivo 0C2_Request.xml en el \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\ Carpeta LOBApplication\SampleInstances y, a continuación, copie y pegue el contenido en el **contenido de servicio** campo LOBWebApplication.  
  
    > [!NOTE]
    >  Para eliminar el texto existente en el campo de contenido de servicio de la forma de enviar el mensaje, coloque el cursor al principio del texto, mantenga presionada la **MAYÚS** y **Ctrl** botones, haga clic en **final** y, a continuación, haga clic en **eliminar**.  
  
4.  Haga clic en **enviar** para enviar el 0 C 2 solicite para el equipo de Contoso.  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Para comprobar que la comunicación es correcta en el equipo de Fabrikam  
  
-   En la página **Estado del mensaje** de LOBWebApplication, compruebe si recibe de dos mensajes entrantes.  
  
    > [!NOTE]
    >  En primer lugar debe recibir un mensaje de 25 de categoría lo que significa una confirmación de recepción desde el equipo de Contoso. A continuación, debería recibir un mensaje de categoría 50 que es el mensaje de respuesta desde el equipo de Contoso. Un mensaje de categoría -99 indica un error. Puede usar **Visor de eventos** para determinar el mensaje de error real.  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Para comprobar que la comunicación es correcta en el equipo de Contoso  
  
1.  Haga clic en **Inicio**, seleccione **Todos los programas**, elija **Microsoft SQL Server**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el cuadro de diálogo **Conectarse al servidor** , en el cuadro **SQL Server** , escriba **localhost**, seleccione **Autenticación de Windows**y, después, haga clic en **Conectar**.  
  
    > [!NOTE]
    >  Si el Agente SQL Server no está iniciado, haga clic con el botón secundario sobre él y después haga clic en **Iniciar**.  
  
3.  En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.  
  
4.  En el \<tabla\> el cuadro de diálogo de texto, seleccione **BTARNDATA** en la lista y, a continuación, haga clic en **Aceptar**.  
  
5.  En la ventana de SQL, escriba la siguiente instrucción SQL:  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  En el **consulta** menú, haga clic en **Execute** para ejecutar la instrucción SQL.  
  
7.  En la ventana de consulta, en el panel de resultados, compruebe que puede ver dos mensajes entrantes.  
  
    > [!NOTE]
    >  En primer lugar debe recibir un mensaje de categoría 10 que representa la solicitud original enviada por el equipo de Fabrikam. A continuación, debería recibir un mensaje de 25 de categoría lo que significa el mensaje de confirmación de recepción.  
  
8.  En la ventana de SQL, escriba la siguiente instrucción SQL:  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. Haga clic en **Ejecutar** para ejecutar la instrucción SQL.  
  
10. En la ventana de consulta, en el panel de resultados, compruebe que ve un mensaje saliente.  
  
    > [!NOTE]
    >  Debería ver un mensaje de 25 de categoría que representa la confirmación de recepción enviada desde Contoso en el equipo de Fabrikam. También verá un mensaje de categoría 50 que representa la respuesta enviada desde la aplicación de Contoso línea de negocio (LOB) en el equipo de Fabrikam.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Enviar un 0c consultar 4](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md)   
 [Flujo de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)