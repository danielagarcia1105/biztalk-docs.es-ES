---
title: Invocar una directiva desde otra directiva | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5bf658a-02a1-426a-abe5-8c9de673cf0d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac45c31ef76213e79249e96fe645ecbb5fb66ed4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973562"
---
# <a name="invoking-a-policy-from-another-policy"></a>Invocar una directiva desde otra directiva
Puede invocar una directiva (secundaria) desde otra directiva (principal) mediante el uso de uno de los siguientes métodos:  
  
-   Llamar a la **Policy.Execute** (método) directamente desde la directiva principal  
  
-   Llamar a un método de un componente .NET auxiliar que ajusta la **Policy.Execute** método desde la directiva principal  
  
 La ventaja de usar el segundo método es que puede agregar código previas y posteriores al procesamiento para la **Policy.Execute** método. Por ejemplo, puede crear cualquier hecho necesario desde la directiva secundaria en este método contenedor. Las siguientes secciones proporcionan un ejemplo para cada método.  
  
## <a name="invoking-the-policyexecute-method-directly-from-the-parent-policy"></a>Invocar el método Policy.Execute directamente desde la directiva principal  
 En esta sección se detallan los pasos de alto nivel para invocar la directiva secundaria desde la directiva principal mediante la **Policy.Execute** método directamente.  
  
### <a name="adding-the-policyexecute-action-to-the-parent-policy"></a>Agregar la acción Policy.Execute a la directiva principal  
 El procedimiento siguiente tiene pasos para agregar el **Policy.Execute** método como una acción a la directiva principal que transfiere un documento XML como un hecho a la directiva secundaria.  
  
##### <a name="to-add-the-policyexecute-method-as-an-action-to-a-policy"></a>Para agregar el método Policy.Execute como acción a una directiva  
  
1.  En la ventana Explorador de hechos, haga clic en el **clases .NET** ficha.  
  
2.  Haga clic en **ensamblados .NET**y, a continuación, haga clic en **examinar**.  
  
3.  Seleccione **Microsoft.RuleEngine** desde el **ensamblados .NET** lista y, a continuación, haga clic en **Aceptar**.  
  
4.  Expanda **directiva**.  
  
5.  Arrastre **Execute (Object facts)** o **Execute (Object facts, IRuleSetTrackingInterceptor trackingInterceptor)** al panel entonces.  
  
6.  Haga clic en el **esquemas XML** nodo.  
  
    > [!NOTE]
    >  En este escenario de ejemplo, un documento XML que se envía como un hecho a la directiva principal se transfiere como hecho a la directiva secundaria. En lugar de ello, puede invocar un método .NET que cree los hechos para la directiva secundaria.  
  
7.  Haga clic en **esquemas**y, a continuación, haga clic en **examinar**.  
  
8.  Seleccione el esquema del documento XML que desea transferir como hecho y, a continuación, haga clic en **abiertos**.  
  
9. Arrastre  *\<nombre de esquema\>*.xsd al primer argumento de la **Policy.Execute** método para pasar el documento XML que se pasa a la directiva principal como un hecho a la directiva secundaria.  
  
10. Si usas el **Execute** método que no tome el **IRuleSetTrackingInterceptor** como segundo argumento, omita los pasos siguientes.  
  
11. Haga clic en el **clases .NET** ficha.  
  
12. Arrastre **DebugTrackingInterceptor** en **Microsoft.RuleEngine** para el segundo argumento de la **Policy.Execute** método.  
  
    > [!NOTE]
    >  Si realiza esta acción, el cliente debe pasar una instancia de la **DebugTrackingInterceptor** clase como un hecho a la directiva principal, que a su vez pasa la instancia como un hecho a la directiva secundaria. En su lugar, puede arrastrar el constructor de la **DebugTrackingInterceptor** clase para que la instancia se crea automáticamente.  
  
### <a name="modifying-the-client-application-that-invokes-the-parent-policy"></a>Modificar la aplicación cliente que invoca la directiva principal  
 El cliente que invoca la directiva principal crea una instancia de la **directiva** clase con el nombre de la directiva secundaria como parámetro y lo pasa como un hecho a la directiva principal junto con otros hechos. En el siguiente código de ejemplo se ilustra esta acción:  
  
```  
DebugTrackingInterceptor dti = new DebugTrackingInterceptor("PolicyTracking.txt");  
Policy policy = new Policy("ParentPolicy");  
object[] facts = new object[3];  
facts[0] = txd;  
facts[1] = new Policy("ChildPolicy");  
facts[2] = new DebugTrackingInterceptor("PolicyTracking2.txt");  
policy.Execute(facts, dti);  
policy.Dispose();  
```  
  
 Si el cliente es una orquestación de BizTalk, debe colocar el código para crear hechos en un **expresión** forma y, a continuación, transferirlos como parámetros a la **reglas de llamada** forma.  
  
## <a name="invoking-a-net-wrapper-method-from-the-parent-policy"></a>Invocar un método contenedor .NET desde la directiva principal  
 En esta sección se detallan los pasos de alto nivel para invocar un método de .NET que contiene la llamada a la **Policy.Execute** método desde la directiva principal.  
  
### <a name="creating-the-utility-net-class"></a>Crear la clase de utilidad .NET  
  
##### <a name="to-create-the-utility-class"></a>Para crear la clase de utilidad  
  
1.  Cree un proyecto de biblioteca de clases .NET y, a continuación, agregue una clase al proyecto.  
  
2.  Agregue un método estático que llama el **Policy.Execute** método que se invoca la directiva cuyo nombre se pasa como un parámetro, tal como se muestra en el código de ejemplo siguiente:  
  
    ```  
    public static void Execute(string policyName, TypedXmlDocument txd)  
    {  
        DebugTrackingInterceptor dti = new   DebugTrackingInterceptor("PolicyTracking.txt");  
        Policy policy = new Policy("ParentPolicy");  
        object[] facts = new object[3];  
        facts[0] = txd;  
        facts[1] = new Policy("ChildPolicy");  
        facts[2] = new DebugTrackingInterceptor("PolicyTracking2.txt");  
        policy.Execute(facts, dti);  
        policy.Dispose();  
    }   
    ```  
  
3.  Asegúrese de que el **StaticSupport** clave del registro se establece en 1 o 2. Para obtener más información acerca de la clave del registro, consulte [invocar miembros estáticos de una clase](../core/invoking-static-members-of-a-class.md).  
  
    > [!NOTE]
    >  Puede usar un método de instancia en lugar de un método estático. Recuerde que si usa un método de instancia, el cliente debe transferir una instancia de la clase .NET auxiliar como hecho a la directiva principal.  
  
### <a name="modifying-the-client-application"></a>Modificar la aplicación cliente  
 El cliente invoca la directiva principal y ésta invoca el método auxiliar que invoca la directiva secundaria. El código de ejemplo para el cliente es el siguiente:  
  
```  
facts[0] = txd;  
facts[1] = new PolicyExecutor(txd);  
//call the first or parent policy  
Policy policy = new Policy(policyName);  
DebugTrackingInterceptor dti = new DebugTrackingInterceptor("PolicyTracking.txt");  
policy.Execute(facts, dti);  
policy.Dispose();  
```  
  
> [!NOTE]
>  Si el método es de instancia, el cliente debe crear una instancia de la clase .NET auxiliar y transferirla como hecho a la directiva principal.  
  
> [!NOTE]
>  Si el cliente es una orquestación de BizTalk, debe colocar el código para crear hechos en un **expresión** forma y, a continuación, transferirlos como parámetros a la **reglas de llamada** forma.