---
title: Cómo finalizar un adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfba2b61-b89f-41cd-a014-4e96daec6516
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd2621e15803dd5f6e8f449de530e84df1bc1b9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255996"
---
# <a name="how-to-terminate-an-adapter"></a>Cómo finalizar un adaptador
Los temas siguientes sirven de guía para el correcto apagado de un adaptador.  
  
## <a name="terminating-an-adapter"></a>Finalizar un adaptador  
 Cuando se va a cerrar el motor de mensajería llama al método **IBTTransportControl**. **Terminar** en cada adaptador de tipo en curso. Una vez que vuelva este método, BizTalk Server destruirá el adaptador. Esto ocurre inmediatamente con los adaptadores nativos, pero en el caso de los adaptadores administrados puede llevar más tiempo debido al proceso de recolección de elementos no utilizados de .NET. El adaptador debe bloquear **Terminate** y realice cualquier sea necesario hasta que esté listo para ser destruido el trabajo de limpieza.  
  
## <a name="terminating-isolated-receive-adapters"></a>Finalizar adaptadores de recepción aislados  
 Aisladas de recepción no tiene adaptadores de **Terminate** en las mismas llama porque no se hospedan en el servicio de BizTalk. En su lugar, debe llamar a **IBTTransportProxy**. **TerminateIsolatedReceiver** para notificar al motor de mensajería que va a apagar.  
  
## <a name="clean-up-com-objects-by-using-marshalreleasecomobject"></a>Limpiar objetos COM mediante Marshal.ReleaseComObject  
 Cuando se escribe código administrado que usa objetos COM, Common Language Runtime (CLR), genera objetos proxy que conservan las referencias a dichos objetos COM. Los objetos proxy son objetos administrados y están sujetos a las reglas habituales de recolección de elementos no utilizados. Existe el problema de que el recolector de elementos no utilizados solo ve la memoria asignada por los tiempos de ejecución de .NET y no es consciente del objeto COM. Los objetos proxy son pequeños, por lo que un objeto COM grande podría quedar en memoria si el recolector CLR de elementos no utilizados no tiene constancia de él.  
  
 Para evitar este problema, libere explícitamente los objetos COM subyacentes cuando termine con ellos, especialmente cualquier **IBTTransportBatch** objetos. Para ello, al llamar a **Marshal**. **ReleaseComObject**.  
  
> [!NOTE]
>  **ReleaseComObject** devuelve el número de referencias restantes y solo libera el objeto COM cuando dicho valor es cero. A menudo **ReleaseComObject** se llama en un bucle para asegurarse de que se libera el objeto. Una vez que completa, debe llamar a **SuppressFinalize** en este objeto porque no hay nada que finalizar. El último paso consiste en comprobar si el objeto es realmente un objeto COM.  
  
 El código siguiente muestra el proceso que se acaba de describir:  
  
```  
if (Marshal.IsComObject (batch))  
(  
While (0 <Marshal.ReleaseComObject(batch)  
;  
GC.SuppressFinalize (batch);  
  
```  
  
 Liberar de forma explícita el **IBTTransportBatch** objeto devuelto desde **GetBatch** puede realizar una mejora considerable del rendimiento.  
  
## <a name="always-use-terminate-when-closing-an-adapter"></a>Usar siempre Terminate al cerrar un adaptador  
 Para que BizTalk Server reconozca su código como un adaptador, debe implementar una interfaz denominada **IBTTransportControl**. Esa interfaz regula el modo en que BizTalk Server se comunica con su adaptador, y se define de este modo:  
  
```  
public interface IBTTransportControl   
{  
void Initialize(IBTTransportProxy transportProxy);  
void Terminate();  
}  
```  
  
 La interfaz contiene dos métodos, **inicializar** y **Terminate**.  
  
### <a name="initialize"></a>Inicializar  
 BizTalk Server llama a la **inicializar** método tras cargar el ensamblado del adaptador. Hace esto con el fin de pasar el proxy de transporte (el principal componente de BizTalk Server) al adaptador. La implementación de **inicializar** simplemente almacena el proxy de transporte en una variable miembro.  
  
### <a name="terminate"></a>Finalizar  
 BizTalk Server llama a la **Terminate** método de cierre del servicio para dar tiempo al adaptador para finalizar la ejecución de todos los lotes. Esto hace que la implementación de la **Terminate** método mucho más compleja.  
  
 El adaptador no debe devolver desde una **Terminate** llamadas hasta que se complete cualquier trabajo pendiente tiene. Cuando BizTalk Server llama **Terminate**, el adaptador debería intentar detener todas sus tareas actuales y no iniciar ninguna nueva.  
  
 Dado que **Terminate** se llama como parte del cierre del servicio, el Administrador de control de servicios finaliza el proceso si el adaptador de bloquearse en **Terminate**. En ese caso, verá la advertencia del Administrador de control de servicios cuando éste detenga el servicio de BizTalk Server. Si es posible, no finalice el adaptador de este modo prematuro. Si el adaptador no realiza correctamente el proceso de finalización y aún tiene subprocesos en ejecución cuando el proceso comienza a finalizar, puede que a veces vea un mensaje de infracción de acceso de BizTalk Server al apagar.  
  
 Dada la naturaleza asíncrona de la interfaz con BizTalk Server, es probable que bajo la carga aún haya muchos lotes y por tanto subprocesos en ejecución. El **Terminate** llamada debe implementarse para esperar la finalización de cada lote se ha ejecutado correctamente el adaptador en BizTalk Server antes de continuar. La conclusión del lote se señaliza mediante la **BatchComplete** devolución de llamada de BizTalk Server. El **Terminate** debe esperar la llamada cada pendientes **BatchComplete** que se produzca. No obstante, el lote debe ejecutarse correctamente. Es decir, la llamada a **IBTTransportBatch**::**realiza** no producirá un error. Si la llamada a **IBTTransportBatch**::**realiza** se produce un error, no hay ninguna devolución de llamada de lote.  
  
 Una vez comprendido que debe agregar código de sincronización a su adaptador, la implementación es bastante sencilla.  
  
 Una estrategia sencilla consiste en implementar un objeto de sincronización compuesta con **escriba** y **deje** métodos para los subprocesos de trabajo y un **finalizar** método que se bloquee mientras un subproceso está aún dentro de la ejecución protegida. (A propósito, la solución es muy similar a la estructura de varios lectores, solo escritor familiar donde los subprocesos de trabajo pueden considerarse como lectores y **finalizar** método como el sistema de escritura.)  
  
 El **finalizar** método es como sigue:  
  
```  
void terminate ()  
{  
this.control.Terminate();  
}  
```  
  
 Para cada subproceso de trabajo:  
  
```  
If (!this.control.Enter())  
return; // we can’t enter because Terminate has been called  
try  
{  
//  create and fill batch  
batch.Done();  
}  
catch (Exception)  
{  
//  we are not expecting a callback  
This.control.Leave();  
}  
```  
  
 En la devolución de llamada de BizTalk Server:  
  
```  
batchComplete (…)  
{  
//  the callback from BizTalk Server  
//  process results  
this.control.Leave();  
}  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]se distribuye con el código de ejemplo ControlledTermination.cs en el ejemplo de adaptador Base, que muestra el mecanismo de sincronización que se describen aquí.