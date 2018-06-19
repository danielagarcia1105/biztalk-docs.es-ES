---
title: Usar SSO de forma eficaz en la solución de administración de procesos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, process management solutions
- SSO, configuration values
- caching, configuration values [SSO]
- SSO, caching
- process management solution tutorial, SSO
ms.assetid: 39fbc42d-caa4-4003-a13b-5cde578eb5e1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99575e54b887124bfa4c33fc5257cd057ea818fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288524"
---
# <a name="using-sso-efficiently-in-the-business-process-management-solution"></a>Usar SSO de forma eficaz en la solución de administración de procesos empresariales
Como la solución orientada a servicios, la solución Administración de procesos empresariales utiliza el inicio de sesión único (SSO) empresarial para almacenar valores de configuración como el número de fases de procesamiento de pedido. Utiliza el almacén secreto porque está presente siempre que se instala BizTalk, SSO almacena la información de configuración en caché para que los valores estén fácilmente disponibles y pueda proteger información como cadenas de conexiones de base de datos y contraseñas. Por todas estas razones, el almacén secreto es un buen sitio para la información de configuración incluso si el inicio de sesión único no se estaba utilizando para administrar conexiones a las aplicaciones de servidor.  
  
 Para reducir latencia, la solución utiliza una caché local para los valores de configuración. La solución actualiza la caché cada cinco minutos.  
  
 En este tema se describe el mecanismo de almacenamiento en caché que utiliza la solución. Esta solución trata el almacenamiento de SSO en caché de un modo ligeramente diferente al de la solución orientada a servicios. Para obtener una descripción de cómo la solución orientada almacena en caché valores SSO, vea [usar SSO de forma eficaz en la solución orientada a servicios](../core/using-sso-efficiently-in-the-service-oriented-solution.md).  
  
## <a name="caching-configuration-values-locally"></a>Almacenar en caché localmente valores de configuración  
 La solución Administración de procesos empresariales utiliza propiedades en un objeto Singleton para proporcionar acceso a los valores SSO.  
  
> [!NOTE]
>  Recuerde que un objeto Singleton es un objeto que sólo puede tener una instancia. Para obtener más información sobre objetos singleton y su creación en C#, vea [http://go.microsoft.com/fwlink/?LinkId=58806](http://go.microsoft.com/fwlink/?LinkId=58806).  
  
 En la solución, una orquestación primero recupera el objeto singleton y, a continuación, hace referencia a los valores a través de las propiedades del objeto. Este es el código de la **OrderManager** orquestación:  
  
```  
configData = Microsoft.Samples.BizTalk.SouthridgeVideo.Utilities  
                .SsoConfigHelper.Singleton;  
numStages = configData.TotalStages;  
```  
  
 La orquestación llama el **Singleton** método en el **SsoConfigHelper** objeto que se va a obtener acceso a una copia del objeto. Con el objeto en mano, la orquestación recupera el número de fases de procesamiento, **TotalStages**.  
  
 La solución sigue un método común para crear un singleton: marque el constructor como privado, tener el objeto de crear una instancia de sí mismo y asígnela a una variable privada y, a través de un método o propiedad, proporcionan acceso al valor de esa variable. El **SsoConfigHelper** objeto utiliza una propiedad, **Singleton**, para proporcionar acceso a la única copia de sí mismo.  
  
> [!NOTE]
>  El **SsoConfigHelper** objeto utiliza un constructor estático que se va a obtener los valores iniciales de la caché SSO como configurar el mecanismo de actualización. Debido a que no se puede llamar a un constructor estático, éste conserva el diseño Singleton. Para obtener más información sobre los constructores estáticos, vea [http://go.microsoft.com/fwlink/?LinkId=59142](http://go.microsoft.com/fwlink/?LinkId=59142).  
  
 Todos los objetos a los que hace referencia una orquestación ya sea directa o indirectamente, deben serializarse. Para obtener más información, vea "Serialización" en [persistencia y el motor de orquestaciones](../core/persistence-and-the-orchestration-engine.md). Aunque la **SsoConfigHelper** objeto es necesariamente serializable, si el motor deshidrata la orquestación, cuando la orquestación se rehidrate, seguirá usa la instancia única, actual del objeto. Para obtener más información sobre serialización y las variables de servidor BizTalk Server, vea [tipos de variables de orquestación](../core/orchestration-variable-types.md).  
  
> [!NOTE]
>  Todos los métodos públicos en el objeto de la solución orientada a servicios son estáticos. Por lo tanto, la orquestación no necesita asignar una instancia a una variable y no es necesario que se serialice la clase.  
  
 El **SsoConfigHelper** objeto utiliza los mismos mecanismos para recuperar y actualizar los valores de configuración como la solución orientada a servicios. También se utiliza el mismo patrón de bloqueo. Para obtener más información acerca de estos mecanismos, vea [usar SSO de forma eficaz en la solución orientada a servicios](../core/using-sso-efficiently-in-the-service-oriented-solution.md) y el código fuente de **SsoConfigHelper**.  
  
 Al igual que el inicio de sesión único almacenamiento en caché se realiza en la solución orientada a servicios, la solución de administración de procesos empresariales implementa la **IPropertyBag** de la interfaz de la **Microsoft.BizTalk.SSOClient.Interop** espacio de nombres para almacenar los valores. La solución de administración de procesos empresariales utiliza una **HybridDictionary** objeto en lugar de un **NameValueCollection** objeto.  
  
 A diferencia de la solución orientada a servicios, la solución Administración de procesos empresariales expone un objeto con propiedades que corresponden a los datos de configuración. Esto evita que la orquestación tenga que ocuparse de diferencias en los tipos de mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Aspectos destacados de la implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md)