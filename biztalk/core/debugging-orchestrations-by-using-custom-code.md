---
title: Depurar orquestaciones mediante código personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, debugging
- building, debugging
ms.assetid: 94e569fa-8dea-4027-abb5-37b4a8015621
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e32358f48099b9d184a9ff1ff62a0a85af595b89
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995341"
---
# <a name="debugging-orchestrations-by-using-custom-code"></a>Depurar orquestaciones mediante Código personalizado
Si la orquestación que se va a emplear en un entorno de prueba o está creando un prototipo y desea modificar los valores de los campos de mensajes y variables de orquestación, puede escribir la salida a la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] consola mediante el siguiente código en un  **Expresión** forma:  
  
```  
System.Diagnostics.Debug.WriteLine(iResult);  
```  
  
 Tendrá que colocar esto **expresión** forma inmediatamente después de la forma en que realiza la operación para que se pueda pasar el resultado para la depuración.  
  
 Asimismo, puede escribir un depurador personalizado sencillo al crear un archivo DLL de depuración con una clase que incluya un método que tome como entrada un mensaje cuyo formato se haya definido en la orquestación y al que se haya hecho referencia en el archivo DLL de depuración. Para obtener más información acerca de cómo pasar un mensaje como un parámetro, vea [cómo usar expresiones para crear objetos y llamar a métodos del objeto](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md).  
  
 Este método puede abrir un cuadro de diálogo de depuración que incluye un cuadro combinado u otro control que le permite al usuario modificar los valores, volver a reunir los mensajes editados y devolverlos como el valor devuelto.  
  
 Configurar una variable booleana para indicar si la orquestación está en modo de depuración y, después, siempre que tiene un punto en la orquestación a la que le gustaría poder modificar los valores, puede agregar un **decidir** forma con uno en vivo rama que se ejecuta solo cuando la variable de modo de depuración está establecida en True, o cuando se produzca una condición determinada que desea examinar. Se llama al método desde un **expresión** forma en la rama activa de la **decidir**. Cuando ya no necesite depurar, se establece la variable de modo de depuración en False o se quita el **decidir** forma o formas completamente y vuelva a compilar.  
  
## <a name="to-debug-a-net-component-called-by-an-orchestration"></a>Para depurar un componente .NET al que llama una orquestación  
 Los pasos siguientes muestran cómo depurar un componente .NET al que llama una orquestación:  
  
1. Abra el proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para el componente.  
  
2. Configure un punto de interrupción del componente en el método que llama la orquestación.  
  
3. Haga clic en el **depurar** menú y seleccione **asociar al proceso...** para mostrar el **asociar al proceso** cuadro de diálogo.  
  
4. Haga clic en el **seleccione...** situado junto a la **adjuntar a:** cuadro de texto para mostrar el **Seleccionar tipo de código** cuadro de diálogo.  
  
5. Haga clic para seleccionar la opción de **depurar estos tipos de código:** y seleccione **administrada** y, a continuación, haga clic en el **Aceptar** botón.  
  
6. Haga clic para seleccionar el **BTSNTSvc.exe** procesos de **procesos disponibles** y, a continuación, haga clic en el **adjuntar** botón.  
  
7. Envíe un mensaje a la orquestación mediante un puerto de recepción.  
  
8. Se debería detener el componente .NET en el punto de interrupción.  
  
9. Puede realizar la depuración como de costumbre con [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
    > [!NOTE]
    >  Para obtener mejores resultados, se debería registrar el componente .NET en la Caché de ensamblados global (GAC).  
  
## <a name="see-also"></a>Vea también  
 [Interfaz de usuario del depurador de orquestaciones](../core/orchestration-debugger-user-interface.md)   
 [Depuración de orquestaciones](../core/debugging-orchestrations.md)