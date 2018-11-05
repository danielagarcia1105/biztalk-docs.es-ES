---
title: 'Paso 2: Configurar un puerto de envío WCF-WebHttp bidireccional | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0bcab296-7921-4df4-abcc-eea78cc827e8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f355275f9480cfa13f3a15bcc6522fbe7ec83b8c
ms.sourcegitcommit: e172dedfd00d4de3a40c8289f3a97ef65cdadd3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2018
ms.locfileid: "22278892"
---
# <a name="step-2-configure-a-two-way-wcf-webhttp-send-port"></a>Paso 2: Configurar un puerto de envío WCF-WebHttp bidireccional
En este paso, configurará un bidireccional **WCF-WebHttp** puerto de envío para invocar la dirección URL de recursos REST para recuperar los retrasos en las compañías aéreas estadounidenses.  
  
### <a name="to-configure-wcf-webhttp-send-port"></a>Para configurar un puerto de envío WCF-WebHttp  
  
1.  Desde la consola de administración de BizTalk Server, en la **BizTalk Application 1** nodo, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **estático Puerto de envío de petición-respuesta**.  
  
2.  En la pestaña **General** , haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **SendPortRESTAzureMarketPlace**.|  
    |**Tipo**|Seleccione **WCF-WebHttp**.|  
    |**Controlador de envío**|Seleccionar **BizTalkServerApplication**.|  
    |**Canalización de envío**|Seleccione **PassThruTransmit**.|  
    |**La canalización de recepción**|Seleccione **PassThruReceive**.|  
  
     Haga clic en **configurar**.  
  
3.  Desde el **propiedades de transporte de WCF-WebHttp** diálogo cuadro, realice lo siguiente:  
  
    1.  En el **General** ficha, para **dirección (URI)**, escriba `https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/`.  
  
    2.  En la ficha General, para **método HTTP y asignación de dirección URL**, escriba lo siguiente:  
  
        ```  
        <BtsHttpUrlMapping>  
        <Operation Method="GET" Url="/On_Time_Performance" />  
        </BtsHttpUrlMapping>  
  
        ```  
  
         En este caso, **obtener** es el verbo HTTP y **On_Time_Performance** se anexa al URI base para construir una dirección URL de recurso único para que recupere retrasos de vuelos.  
         
         > [!TIP] 
         > En el campo de dirección URL, los caracteres XML especiales se deben "escape". Esto garantiza que los caracteres XML especiales se procesan y conserva el puerto. Por ejemplo, el `&` caracteres especiales deben ser de escape como `&amp;`. 
           >
           >De:`Url=”/Customer?{ID}& group=Location”`
           >
           >
           >Para:`Url=”/Customer?{ID}&amp;group=Location”`
  
    3.  En el **enlaces** ficha, para el **tamaño máximo de mensaje recibido** , a continuación, seleccione un valor lo suficientemente grande. Esto se debe a que normalmente el mensaje de respuesta que contiene el estado del vuelo es considerablemente grande y puede superar el tamaño de mensaje predeterminado especificado.  
  
    4.  En el **seguridad** ficha, realice lo siguiente:  
  
        1.  Para el **modo de seguridad**, seleccione **transporte**.  
  
        2.  Para **tipo de credencial de cliente de transporte**, seleccione **básica**.  
  
        3.  En el **las credenciales de nombre de usuario** cuadro, haga clic en **editar**. En el **las credenciales de cliente** cuadro de diálogo, seleccione **no utilizar inicio de sesión único en**y escriba el nombre de usuario y la contraseña que ha recuperado de la **mi cuenta** pestaña una vez haya iniciar sesión en [Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913). Las credenciales se muestran en la **Id. de cliente** (nombre de usuario) y **clave de cuenta principal** etiquetas (contraseña).  
  
        4.  Haga clic en **Aceptar**.  
  
    5.  En el **mensajes** ficha, para **suprimir el cuerpo para verbos**, especifique el verbo que desea quitar la carga del mensaje del mensaje de solicitud. Para este tutorial, especifique `GET`. Esta es la razón: una llamada de método GET en el extremo REST de US Air Carrier flight retrasos no requiere una carga de mensaje; la dirección URL de recursos REST es suficiente para recuperar la información. Sin embargo, para activar el **WCF-WebHttp** puerto de envío que realiza la llamada REST, se coloca un mensaje ficticio que tiene algunos cuerpo del mensaje. El puerto de envío no debe enviar ese mensaje ficticio al extremo REST porque, tal como se explicó anteriormente, el extremo no espera una carga de mensaje. Por lo tanto, antes de invocar el extremo REST, el adaptador elimina la carga del mensaje del mensaje ficticio solo para los verbos que especifique en el **suprimir el cuerpo para verbos** cuadro de texto.  
  
    6.  Haga clic en **Aceptar** hasta que esté en el cuadro de diálogo Propiedades de puerto de envío. En el panel izquierdo, haga clic en **filtros**y especifique el filtro que se va a consumir todos los mensajes que se reciben a través de la recepción de puerto que ha creado en [paso 1: configurar una ubicación de recepción de archivo](../core/step-1-configure-a-file-receive-location.md).  
  
        |||  
        |-|-|  
        |**Propiedad**|Establecido en **BTS. ReceivePortName**|  
        |**Operador**|Establecido en **==**|  
        |**Valor**|Establecido en`ReceivePortRestAzureMarketPlace`|  
  
    7.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 5: Invocar una interfaz REST con BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)