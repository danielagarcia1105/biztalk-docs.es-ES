---
title: MQSCorrelationSetOrchestration (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- orchestrations, examples
- examples, orchestrations
- examples, messages
- messages, examples
- MQSeries adapters, examples
ms.assetid: fcda65d0-e3ec-4ead-978d-3904903b8762
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ac63fe0fee593f927e854ce425ff7f631f9475
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="mqscorrelationsetorchestration-biztalk-server-sample"></a>MQSCorrelationSetOrchestration (ejemplo de BizTalk Server)
El ejemplo MQSCorrelationSetOrchestration muestra cómo usar el identificador de correlación MQSeries para correlacionar los mensajes enviados a una cola de MQSeries de vuelta a una orquestación en ejecución. La orquestación establece el identificador de correlación de MQSeries y el mensaje valores de identificador mediante la **MQMD_CorrelId** y **MQMD_MsgID** propiedades. El administrador de cola de MQSeries copia el valor de MessageID en la propiedad CorrelationID del mensaje.  
  
## <a name="prerequisites"></a>Requisitos previos  
 En este ejemplo se presupone que ha instalado IBM WebSphere MQSeries en el mismo servidor en el que se ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En este ejemplo se muestra cómo establecer un identificador de mensaje y de correlación en un mensaje enviado a un servidor IBM WebSphere MQSeries Server. Es un método que se puede utilizar para correlacionar un mensaje de vuelta a una instancia de orquestación en ejecución. Cuando el administrador de cola de MQSeries recibe el mensaje, copia el valor de MessageID en la propiedad CorrelationID del mensaje. Este CorrelationID (**MQMD_CorrelId**), a continuación, se utiliza en la orquestación para asociar el mensaje de respuesta en MQSeries con la instancia que se usan para enviar mensajes a MQSeries.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 En este ejemplo se muestra un escenario en el que un documento que una orquestación está procesando puede enviarse a una cola MQSeries (supuestamente para otro procesamiento) y devolverse a la orquestación en ejecución.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso\>*\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|**Archivo**|**Description**|  
|--------------|---------------------|  
|**MQSCorrelationSetOrchestration.btproj,**<br /><br /> **MQSCorrelationSetOrchestration.sln**|Archivos de proyectos y soluciones para la aplicación.|  
|**MQSCorrelationSetOrchestration.odx**|La orquestación de la aplicación.|  
|**MQSCorrelationSetOrchestration.snk**|Archivo de clave de nombre seguro.|  
|**Setup.bat**|Crea e inicializa este ejemplo.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Incorpore la lógica utilizada en este ejemplo si necesita enviar un mensaje a MQSeries Server como uno de los pasos en el flujo de trabajo global.  
  
### <a name="to-create-the-mqseries-queue-through-the-websphere-mq-explorer"></a>Para crear la cola MQSeries mediante WebSphere MQ Explorer  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione **IBM WebSphere MQ**y, a continuación, haga clic en **WebSphere MQ Explorer**.  
  
2.  Haga doble clic en **administradores de cola**y, a continuación, haga doble clic en el Administrador de cola predeterminado. El Administrador de cola predeterminado se suele llamar **QM_ < nombre_equipo >** donde *nombre_equipo* es el nombre del equipo.  
  
3.  Haga clic en **colas**, seleccione **New**y, a continuación, haga clic en **cola Local**.  
  
4.  En **Create Local Queue** cuadro de diálogo **nombre de la cola**, escriba "MQCorrelation" y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>Para crear la ubicación de recepción y la cola de MQSeries  
  
1.  Abra la consola de administración de BizTalk Server.  
  
2.  Expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación necesaria.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
4.  En el **propiedades del puerto de recepción unidireccional** cuadro de diálogo, en la **nombre** cuadro, escriba "MQIn" y haga clic en **Aceptar**.  
  
5.  En el panel izquierdo, haga clic en **ubicaciones de recepción** ficha y, a continuación, haga clic en **nuevo**.  
  
6.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba "MQIn".  
  
7.  En el **tipo de transporte** cuadro, seleccione **MQSeries**.  
  
8.  En el **controlador de recepción** cuadro, seleccione **BizTalkServerApplication**.  
  
9. En el **canalización de recepción** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.  
  
10. Haga clic en **configurar**.  
  
11. En el **propiedades de transporte MQSeries** cuadro de diálogo, en la **intervalo de sondeo** , escriba "10".  
  
12. En el **definición de la cola** cuadro, haga clic en el botón de puntos suspensivos (...).  
  
13. En el **definición de la cola** cuadro de diálogo, en la **nombre del servidor** , escriba el nombre del equipo.  
  
14. En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.  
  
15. En el **cola** , escriba "MQCorrelation" y, a continuación, haga clic en **exportar**.  
  
16. En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en**Aceptar**o **realiza** hasta que haya salido de todos los cuadros de diálogo.  
  
### <a name="to-create-the-send-port-to-mqseries"></a>Para crear el puerto de envío en MQSeries  
  
1.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **nombre** , escriba "MQOut".  
  
3.  En el **tipo de transporte** cuadro, seleccione **MQSeries**.  
  
4.  En el **canalización de envío** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.  
  
5.  Haga clic en **configurar**.  
  
6.  En el **propiedades de transporte MQSeries** cuadro de diálogo, en la **definición de la cola** cuadro, haga clic en el botón de puntos suspensivos (...).  
  
7.  En el **definición de la cola** cuadro de diálogo, en la **nombre del servidor** , escriba el nombre del equipo.  
  
8.  En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.  
  
9. En el **cola** , escriba "MQCorrelation" y, a continuación, haga clic en **Aceptar**.  
  
10. Haga clic en **Aceptar** hasta que haya salido de todos los cuadros de diálogo.  
  
### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>Para habilitar la ubicación de recepción e iniciar el puerto de envío  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**.  
  
2.  En el panel de detalles, haga clic en el **MQIn** ubicación de recepción y haga clic en **habilitar**.  
  
3.  En el panel de detalles, haga clic en el **MQOut** puerto de envío y haga clic en **iniciar.**  
  
### <a name="to-create-the-folders-used-by-the-application"></a>Para crear las carpetas usadas por la aplicación  
  
1.  En su **C:\\**  unidad, cree una carpeta denominada "temp" Si aún no existe.  
  
2.  En el **C:\temp** directorio, cree carpetas denominadas "Pickup" y "Dropit".  
  
### <a name="building-and-deploying-this-sample"></a>Generar e implementar este ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration`  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    1.  Crea una clave de nombre seguro para el proyecto.  
  
    2.  Compila e implementa el proyecto de orquestación.  
  
    3.  Crea un puerto de envío y un puerto de recepción con el adaptador de archivo.  
  
### <a name="bind-and-start-the-orchestration"></a>Enlazar e iniciar la orquestación  
  
1.  En la consola de administración de BizTalk Server, expanda el **orquestaciones** carpeta.  
  
2.  En el panel de detalles, haga clic en el **MQSCorrelationSetOrchestration** orquestación y, a continuación, haga clic en **enlazar**.  
  
3.  Enlace los puertos de orquestación con los siguientes puertos de envío y ubicaciones de recepción:  
  
    |**Puerto de orquestación**|**Puerto de mensajería / ubicación de recepción**|  
    |----------------------------|--------------------------------------------|  
    |FileReceivePort|MQSCorrelationSetOrchestration.FileReceivePort|  
    |MQSeriesResponseReceivePort|MQIn|  
    |MQSeriesRequestSendPort|MQOut|  
    |FileSendPort|MQSCorrelationSetOrchestration.FileSendPort|  
  
4.  Haga clic en **Host**.  
  
5.  En el **Host** cuadro, seleccione **BizTalkServerApplication**y haga clic en **Aceptar**.  
  
6.  En **puertos de envío**, haga clic en **MQSCorrelationSetOrchestration.FileSendPort**y, a continuación, seleccione **iniciar**.  
  
7.  En **ubicaciones de recepción**, haga clic en **MQSCorrelationSetOrchestration.FileReceivePort** y, a continuación, seleccione **habilitar**.  
  
8.  Haga clic en la orquestación y haga clic en **iniciar**.  
  
    > [!NOTE]
    >  Además, iniciar la orquestación da de alta la orquestación de forma automática.  
  
### <a name="to-test-the-application"></a>Para probar la aplicación  
  
1.  Coloque un archivo en el **C:\Temp\Pickup** carpeta.  
  
2.  Examine el archivo de la **C:\Temp\Dropit** carpeta.  
  
    > [!NOTE]
    >  Si deshabilita la **MQIn** ubicación de recepción, puede examinar el mensaje en WebSphere MQ Explorer y observar que se establecen los identificadores de mensaje y correlación. Para ello, inicie la **WebSphere MQ Explorer** y examine el mensaje colocado en el **MQCorrelation** cola. Los identificadores de mensaje y correlación aparecen en la **identificadores** pestaña de la **propiedades de mensaje** cuadro de diálogo.  
  
    > [!NOTE]
    >  En una situación de producción, deseará asignar un identificador único a cada mensaje que se envía a la cola de MQSeries. Esto se puede hacer modificando la forma de expresión en la orquestación. Cambie las líneas siguientes para establecer estas propiedades en un identificador único de 24 bytes:  
    >   
    >  MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = "111213141516171819202122232425262728293031323334";  
    >   
    >  MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = "111213141516171819202122232425262728293031323334";  
    >   
    >  Si desea establecer un identificador de 24 bytes único para estas propiedades, vea la sección **para crear un identificador de 24 bytes único para los mensajes enviados a MQSeries**.  
  
### <a name="to-create-a-unique-24-byte-id-for-messages-sent-to-mqseries"></a>Para crear un identificador de 24 bytes único para mensajes enviados a MQSeries  
  
1.  Cree un proyecto nuevo de biblioteca de clases C# en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
2.  Pegue el código siguiente en el archivo .cs para la clase:  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Security.Cryptography;  
  
    namespace MQId  
    {[Serializable]  
        public class GetId  
        {  
            RNGCryptoServiceProvider randomCryptoString = new RNGCryptoServiceProvider();  
  
            public string getGuidstr()  
            {  
                byte[] newGuid = GetRandomData(24);  
                return ConvertToHex(newGuid);  
            }  
  
            private byte[] GetRandomData(int keySize)  
            {  
                byte[] randomData = new byte[keySize];  
                randomCryptoString.GetBytes(randomData);  
                return randomData;  
            }  
  
            private string ConvertToHex(byte[] key)  
            {  
                StringBuilder hexString = new StringBuilder();  
                for (int i = 0; i < key.Length; ++i)  
                {  
                    hexString.Append(String.Format("{0:X2}", key[i]));  
                }  
                return hexString.ToString();  
            }  
        }  
    }  
    ```  
  
3.  Especifique un **espacio de nombres predeterminado** de **MQId** y **nombre de ensamblado** de **GetId** en las propiedades del proyecto **aplicación**  página.  
  
4.  Especifique un archivo de clave de nombre seguro para firmar el ensamblado en las propiedades del proyecto **firma** página y, a continuación, compile el proyecto.  
  
5.  Use la herramienta de caché global de ensamblados (gacutil.exe) para cargar el ensamblado compilado en la GAC (gacutil /i \< *nombre de archivo dll compilado*\>).  
  
6.  Agregue una referencia al ensamblado GetId en el proyecto de BizTalk para este ejemplo.  
  
7.  Agregue dos variables para la orquestación usada en este ejemplo:  
  
    |Nombre de variable (identificador)|Tipo|  
    |----------------------------------|----------|  
    |GetId|MQId.GetId|  
    |strGuid|System.String|  
  
8.  Pegue el código siguiente en la forma de expresión usada en la orquestación de este ejemplo; este código debe invalidar el código existente:  
  
    ```  
    GetId = new MQId.GetId();  
    strGuid = GetId.getGuidstr();  
    MQSeriesRequestSendMessageModified = MQSeriesRequestSendMessage;  
    MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = strGuid;  
    MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = strGuid;  
    ```  
  
9. Detenga y quite la orquestación de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] si ya está implementada. A continuación, siga los pasos descritos en las secciones **generar e implementar este ejemplo**, **enlazar e iniciar la orquestación** y **para probar la aplicación**.  
  
    > [!NOTE]
    >  El uso de este método para crear un identificador de 24 bytes único para los mensajes enviados a MQSeries no garantiza al 100% identificadores únicos para todos los mensajes que se envían, pero la probabilidad de identificadores de mensaje duplicados es muy baja. Si las necesidades empresariales requieren una garantía al 100% de que no se duplicará ningún identificador de mensaje, entonces será necesario implementar un código personalizado diferente para garantizar esta funcionalidad.  
  
## <a name="classes-or-methods-used-in-this-sample"></a>Clases o métodos usados en el ejemplo  
 En este ejemplo no se utilizan de manera explícita ninguna clase o método.  
  
## <a name="see-also"></a>Vea también  
 [Correlacionar mensajes mediante la solicitud y respuesta](../core/correlating-messages-using-request-reply.md)   
 [Ejemplos del adaptador de MQSeries](../core/mqseries-adapter-samples.md)