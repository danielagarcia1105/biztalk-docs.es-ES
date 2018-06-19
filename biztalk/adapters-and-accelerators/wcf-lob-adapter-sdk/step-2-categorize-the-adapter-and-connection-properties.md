---
title: 'Paso 2: Clasificar las propiedades de conexión y adaptador | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45b3dc64-2078-4008-878b-501f727f4a11
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e9d49323695b1070a8065cf7a5e548e61fc5db9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226828"
---
# <a name="step-2-categorize-the-adapter-and-connection-properties"></a>Paso 2: Clasificar los adaptadores y las propiedades de conexión
![Paso 2 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")  
  
 **Tiempo en completarse:** 30 minutos  
  
 En este paso, va a actualizar el **EchoAdapterBindingElement** y **EchoAdapterBindingElementExtensionElement** clases para asignar una categoría a las propiedades del adaptador y la conexión. Al hacerlo, propiedades se agrupan lógicamente por categoría en la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] herramientas. Por ejemplo, si desea que la **aplicación**, **EnableAuthentication**, y **Hostname** propiedades que aparecen en la **conexión** categoría tal y como se muestra a continuación, debe asignar la categoría de conexión para cada una de las propiedades de la aplicación, EnableAuthentication y nombre de host.  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c7c0c013-6651-4c32-9f8b-b546a68a0267.gif "c7c0c013-6651-4c32-9f8b-b546a68a0267")  
  
 De forma similar, si desea que la **InboundFileFilter** y **InboundFleSystemWatcherFolder** propiedades que aparecen en la **entrada** categoría tal y como se muestra a continuación, necesita Asigne la categoría de entrada a cada uno. Si desea que **recuento** y **EnableConnectionPooling** aparecerá bajo la **varios** categoría, es necesario asignar la categoría de varios a cada uno.  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2acb7677-8b50-4e45-96a3-42d0e2011f19.gif "2acb7677-8b50-4e45-96a3-42d0e2011f19")  
  
 Tenga en cuenta que puede asignar una propiedad con cualquier nombre de categoría que elija. En este ejemplo, puesto que la propiedad EnableConnnectionPooling no pertenece a ninguna otra categoría, se clasificarla como varios (varios). En cuanto a la propiedad InboundFileFilter, ya que se utiliza durante el control de entrada en el ejemplo, es más adecuado asignar la entrada a la propiedad, en lugar de varios. Aquí está la categorización completo de la propiedad personalizada para el adaptador de eco.  
  
|**Propiedad**|**Categoría**|  
|------------------|------------------|  
|InboundFileFilter|Entrada|  
|InboundFileSystemWatcherFolder|Entrada|  
|Count|Varios|  
|EnableConnectionPooling|Varios|  
|Aplicación|Conexión|  
|EnableAuthentication|Conexión|  
|Hostname|Conexión|  
|EchoInUpperCase|Formato|  
  
 Además de estos cambios, también se modifica el método de eliminación de **EchoAdapterHandlerBase**.  
  
 Para las propiedades de adaptador expuestas por el adaptador de eco, vea la sección de propiedades del adaptador de la [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de comenzar este paso, debe completar [paso 1: usar el Asistente de desarrollo de adaptador LOB de WCF para crear el proyecto de adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md). También debe estar familiarizado con la `System.ServiceModel.Configuration.BindingElementExtensionElement` y `System.ServiceModel.Configuration.StandardBindingElement` clases.  
  
## <a name="update-the-echoadapterhandlerbase-dispose-method"></a>Actualizar el método EchoAdapterHandlerBase Dispose  
  
1.  En **el Explorador de soluciones**, haga doble clic en el **EchoAdapterHandlerBase.cs** archivo.  
  
2.  Quite la instrucción siguiente de la **Dispose** método:  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     El método revisado debe ser similar al siguiente:  
  
    ```csharp  
    protected virtual void Dispose(bool disposing)  
    {  
       //  
       //TODO: Implement Dispose. Override this method in respective Handler classes  
       //  
    }  
    ```  
  
## <a name="update-the-adapter-properties-class"></a>Actualización de la clase de propiedades de adaptador  
  
1.  En **el Explorador de soluciones**, haga doble clic en el **EchoAdapterBindingElement.cs** archivo.  
  
2.  En el editor de Visual Studio, expanda la **Custom Properties genera** región.  
  
3.  Para asignar el **varios** categoría a la **recuento** propiedad, agregue la siguiente instrucción única al principio de la **recuento** implementación.  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
     El **recuento** implementación ahora debe coincidir con lo siguiente:  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("count", DefaultValue = 5)]  
    public int Count  
    {  
        get  
        {  
            return ((int)(base["Count"]));  
        }  
        set  
        {  
            base["Count"] = value;  
        }  
    }  
    ```  
  
4.  Para asignar el **varios** categoría a la **EnableConnectionPooling** propiedad, agregue la siguiente instrucción única al principio de la **EnableConnectionPooling** implementación de.  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
5.  Para asignar el **entrada** categoría a la **InboundFileFilter** propiedad, agregue la siguiente instrucción única al principio de la **InboundFileFilter** implementación.  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
6.  Para asignar el **entrada** categoría para **inboundFleSystemWatcherFolder** propiedad, agregue la siguiente instrucción única al principio de la **inboundFleSystemWatcherFolder**implementación.  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
7.  Asegúrese de que el código de la **genera las propiedades personalizadas** región coincide con lo siguiente:  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("count", DefaultValue = 5)]  
    public int Count  
    {  
        get  
        {  
            return ((int)(base["Count"]));  
        }  
        set  
        {  
            base["Count"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("enableConnectionPooling", DefaultValue = true)]  
    public bool EnableConnectionPooling  
    {  
        get  
        {  
            return ((bool)(base["EnableConnectionPooling"]));  
        }  
        set  
        {  
            base["EnableConnectionPooling"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("Inbound")]  
    [System.Configuration.ConfigurationProperty("inboundFileFilter", DefaultValue = "*.txt")]  
    public string InboundFileFilter  
    {  
        get  
        {  
            return ((string)(base["InboundFileFilter"]));  
        }  
        set  
        {  
            base["InboundFileFilter"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("Inbound")]  
    [System.Configuration.ConfigurationProperty("inboundFileSystemWatcherFolder", DefaultValue = "{InboundFileSystemWatcherFolder}")]  
    public string InboundFileSystemWatcherFolder  
    {  
        get  
        {  
            return ((string)(base["InboundFileSystemWatcherFolder"]));  
        }  
        set  
        {  
            base["InboundFileSystemWatcherFolder"] = value;  
        }  
    }  
  
    #endregion Custom Generated Properties  
    ```  
  
## <a name="update-the-connection-properties"></a>Actualizar las propiedades de conexión  
  
1.  En **el Explorador de soluciones**, haga doble clic en el **EchoAdapterConnectionUri.cs** archivo.  
  
2.  En el editor de Visual Studio, expanda la **Custom Properties genera** región.  
  
3.  Para asignar el **formato** categoría a la **EchoInUpperCase** propiedad, agregue la siguiente instrucción única al principio de la **EchoInUpperCase** implementación.  
  
    ```csharp  
    [System.ComponentModel.Category("Format")]  
    ```  
  
4.  Para asignar el **conexión** categoría a la **Hostname** propiedad, agregue la siguiente instrucción única al principio de la **Hostname** implementación.  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
5.  Para asignar el **conexión** categoría a la **aplicación** propiedad, agregue la siguiente instrucción única al principio de la **aplicación** implementación.  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
6.  Para asignar el **conexión** categoría para **EnableAuthentication** propiedad, agregue la siguiente instrucción única al principio de la **EnableAuthentication** implementación de.  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
7.  Asegúrese de que el código de la **genera las propiedades personalizadas** región coincide con lo siguiente:  
  
    ```csharp  
    #region Custom Generated Properties  
            [System.ComponentModel.Category("Format")]  
            public bool EchoInUpperCase  
            {  
                get  
                {  
                    return this.echoInUpperCase;  
                }  
                set  
                {  
                    this.echoInUpperCase = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public string Hostname  
            {  
                get  
                {  
                    return this.hostname;  
                }  
                set  
                {  
                    this.hostname = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public string Application  
            {  
                get  
                {  
                    return this.application;  
                }  
                set  
                {  
                    this.application = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public bool EnableAuthentication  
            {  
                get  
                {  
                    return this.enableAuthentication;  
                }  
                set  
                {  
                    this.enableAuthentication = value;  
                }  
            }  
            #endregion Custom Generated Properties  
    ```  
  
8.  En Visual Studio, desde la **archivo** menú, haga clic en **guardar todo**.  
  
> [!NOTE]
>  Ya ha guardado su trabajo. Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 3: implementar la conexión para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).  
  
## <a name="what-did-i-just-do"></a>¿Simplemente lo que hacía?  
 Que acaba de actualizar las clases para asignar una categoría a cada propiedad de conexión y adaptador expuesta por el adaptador de eco.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Implementar conexión, explorar metadatos, buscar y resolver las capacidades y el intercambio de mensajes salientes. Por último, generará e implementará el adaptador de eco.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Implementar la conexión para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)   
 [Tutorial 1: Desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)