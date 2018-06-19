---
title: Crear MSMQ ubicaciones de recepción y puertos de envío de código | Documentos de Microsoft
description: Crear mediante programación MSMQ ubicaciones de recepción y puertos de envío en el servidor BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ebb4119-deeb-4287-aa65-7597ff0cc435
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5f00a0bfe14eeb7d4205973b3fef96e23026616
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971674"
---
# <a name="create-msmq-receive-locations-and-send-ports-programmatically"></a>Crear ubicaciones de recepción de MSMQ y puertos de envío mediante programación
En este tema se explica cómo usar WMI para crear un puerto o una ubicación para el adaptador de MSMQ.  
  
 Para obtener más información, consulte **crear una ubicación de recepción con una fecha y hora programación configuración mediante WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="setting-property-values"></a>Configurar valores de propiedad  
 El proceso de creación un puerto o una ubicación es siempre el mismo:  
  
1.  Crear un objeto del tipo adecuado.  
  
2.  Establecer el valor de propiedades en el objeto.  
  
3.  Confirmar los valores del objeto en la base de datos.  
  
 Todos los adaptadores tienen determinadas propiedades, como **HostName**en común. Establezca estas propiedades comunes mediante su asignación directa en el objeto. En el siguiente código C# se muestra un caso típico:  
  
```  
objReceiveLocation["HostName"] = "BizTalkServerApplication";  
```  
  
 Asigne los valores a las propiedades que no comparten todos los adaptadores. Cree un documento XML en una cadena y asigne dicha cadena a la propiedad CustomCfg. En el siguiente código C# se muestra un caso típico para un adaptador de archivos:  
  
```  
objReceiveLocation["CustomCfg"] =   
        @"<CustomProps>"  
        + @"<BatchSize>20</BatchSize>"  
        + @"<FileMask>*.xml</FileMask>"  
        + @"<FileNetFailRetryCount>5</FileNetFailRetryCount>"  
        + @"<FileNetFailRetryInt>5</FileNetFailRetryInt>"  
        + @"</CustomProps>";  
```  
  
 Los nombres de las etiquetas del elemento CustomProps son nombres internos que el adaptador utiliza para las propiedades.  
  
 El adaptador de MSMQ tiene una única etiqueta, AdapterConfig, dentro de la etiqueta CustomProps. La etiquete AdapterConfig contiene una cadena de etiquetas XML para los valores de propiedad personalizados incluidos en una etiqueta Config. Sin embargo, las etiquetas están incluidas: "&lt;"reemplaza"\<"y"&gt;"reemplaza"\>". Por ejemplo, el XML de un subconjunto del adaptador de propiedades de MSMQ puede aparecer de la siguiente forma:  
  
```  
<Config>  
    <batchSize>40</batchSize>  
</Config>  
```  
  
 Tenga en cuenta que la **vt** no se utiliza el atributo. La cadena asignada a la **CustomCfg** propiedad como se indica a continuación aparece después de la codificación:  
  
```  
<CustomProps><AdapterConfig vt="8"><Config><batchSize>40</batchSize></Config></AdapterConfig></CustomProps>  
```  
  
## <a name="custom-property-names"></a>Nombres de propiedades personalizadas  
 La tabla siguiente describe los nombres internos del adaptador de MSMQ **enviar** propiedades personalizadas.  
  
|**Enviar el nombre de propiedad personalizada**|**Nombre para mostrar**|  
|-----------------------------------|----------------------|  
|acknowledgeType|Tipo de confirmación|  
|administrationQueue|Cola de administración|  
|certificado|Huella digital de certificado|  
|encryptionAlgorithm|Algoritmo de cifrado|  
|maximumMessageSize|Tamaño máximo de mensaje (en KB)|  
|password|Contraseña|  
|priority|Prioridad del mensaje|  
|cola|Cola de destino|  
|recuperable|Recoverable|  
|segmentationSupport|Admitir segmentación|  
|sendBatchSize|Tamaño del lote|  
|sendQueueName|Cola de destino|  
|timeOut|Timeout|  
|timeOutUnits|Unidad de tiempo de espera|  
|transaccional|Transaccional|  
|useAuthentication|Utilizar autenticación|  
|useDeadLetterQueue|Usar cola de mensajes con problemas de entrega|  
|useJournalQueue|Usar cola de diario|  
|userName|Nombre de usuario|  
  
 La tabla siguiente describe los nombres internos del adaptador de MSMQ **recepción** propiedades personalizadas.  
  
|**Recibe el nombre de propiedad personalizada**|**Nombre para mostrar**|  
|--------------------------------------|----------------------|  
|batchSize|Tamaño del lote|  
|Contraseña|Contraseña|  
|Cola|Cola|  
|serialProcessing|Procesamiento en serie|  
|Transaccional|Transaccional|  
|userName|Nombre de usuario|  
  
## <a name="sample-code"></a>Código muestra  
 El siguiente programa C# crea una ubicación de recepción única para el adaptador de MSMQ. Se supone que el puerto de recepción, ReceivePort1, sale y usa una función auxiliar para codificar y aplicar el formato a las propiedades personalizadas.  
  
```  
using System;  
using System.Management;  
using System.Text;  
  
namespace CreateReceive  
{  
    ///   
    /// Program to create a receive location.  
    ///   
    class CreateReceive  
    {  
        /// The main entry point for the application.  
  
        [STAThread]  
        static void Main()  
        {  
            // Custom properties & values  
            string cfg =   
                    @"<queue>FORMATNAME:DIRECT=OS:MYMACHINE02\PRIVATE$\QUEUE2</queue>"  
                    + @"<batchSize>40</batchSize>"  
                    + @"<transactional>true</transactional>"  
                    + @"<serialProcessing>false</serialProcessing>";  
  
            CreateReceiveLocation (  
                    "Code Created Location",  
                    "ReceivePort1",  
                    "MSMQ",  
                    "BizTalkServerApplication",  
                    EncodeCustomProps(cfg),  // Encode the custom props  
                    "Microsoft.BizTalk.DefaultPipelines.PassThruReceive,"   
                            + " Microsoft.BizTalk.DefaultPipelines,"   
                            + " Version=3.0.1.0, Culture=neutral,"   
                            + " PublicKeyToken=31bf3856ad364e35",  
                    @"FORMATNAME:DIRECT=OS:MYMACHINE\PRIVATE$\QUEUE2"  
                );  
  
        }  
  
        static string EncodeCustomProps (string cp) {  
  
            // Enclose the properties and values in a Config> tag.  
            StringBuilder tmp = new StringBuilder( @"<Config>" + cp + @"</Config>");  
  
            // Encode the string  
            tmp = tmp.Replace("<","<");  
            tmp = tmp.Replace(">",">");  
  
            return (  
                // Enclose the encoded string with necessary tags  
                "<CustomProps><AdapterConfig vt=\"8\">"  
                + tmp.ToString()   
                + "</AdapterConfig></CustomProps>");  
  
        }  
  
        static void CreateReceiveLocation (  
            string name,            // Location name  
            string port,            // Receive port, already exists  
            string adapterName,     // The transport type  
            string hostName,        // BTS host  
            string customCfg,       // Encoded custom properties  
            string pipeline,        // Full specification of pipeline  
            string inboundTransport)// Inbound transport url  
        {  
            try   
            {  
                // Create options to store options in management object  
                PutOptions options = new PutOptions();  
                options.Type = PutType.CreateOnly;  
  
                // Create a management object  
                // Get the class  
                ManagementClass objReceiveLocationClass =   
                           new ManagementClass(  
                               "root\\MicrosoftBizTalkServer",   
                               "MSBTS_ReceiveLocation",   
                               null);  
                // Create an instance of the member of the class  
                ManagementObject objReceiveLocation =  
                          objReceiveLocationClass.CreateInstance();  
  
                // Fill in the properties  
                objReceiveLocation["Name"] = name;  
                objReceiveLocation["ReceivePortName"] = port;  
                objReceiveLocation["AdapterName"] = adapterName;  
                objReceiveLocation["HostName"] = hostName;  
                objReceiveLocation["PipelineName"] = pipeline;  
                objReceiveLocation["CustomCfg"] = customCfg;  
                objReceiveLocation["IsDisabled"] = true;  
                objReceiveLocation["InBoundTransportURL"] = inboundTransport;  
  
                // Put the options -- creates the receive location  
                objReceiveLocation.Put(options);  
            }  
            catch (Exception excep)  
            {  
                System.Console.WriteLine("Create Receive Location ({0}) failed - {1}",  
                                                name, excep.Message);  
            }  
        }  
    }  
}  
```