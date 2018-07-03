---
title: Escenario de cadena de suministro de ejemplo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- supply chains, examples
- examples, supply chains
ms.assetid: 1837a2c8-b1d4-4e1f-a196-a48b13b22662
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f242da434e2f9c6a99ed1f3b27745885188d23e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973509"
---
# <a name="sample-supply-chain-scenario"></a>Escenario de cadena de suministro de ejemplo
Uno de los procesos más importantes en la cadena de suministro de alta tecnología es el intercambio de mensajes de solicitud y respuesta de pedido de compra. Un comprador envía un pedido de compra y lo confirma un proveedor, en el nivel de línea, si acepten o rechacen el pedido, o si el pedido está pendiente.  
  
 En este tema se describe un escenario de ejemplo de dos socios comerciales el intercambio de mensajes de pedido de compra y se muestra cómo mejoran el proceso de la integración y automatización.  
  
## <a name="the-players"></a>Los jugadores  
 El comprador en este escenario de ejemplo es un fabricante de equipos grandes de alta tecnología. Un sistema basado en EDI que utilizan actualmente para el intercambio de datos automatizada. Con los proveedores que no utilizan EDI, que se basan en el teléfono, fax, correo electrónico con hojas de cálculo y aplicaciones Web. Incluso con esos proveedores que utilicen EDI, tienen una capacidad limitada para integrar sus comunicaciones de socios comerciales con su sistema ERP de back-end. Después de recibir pedidos e información a través de EDI, clave que se deben manualmente volver a los pedidos en su sistema ERP. Desean mejorar los procesos existentes de la cadena de suministro mediante la automatización de la demanda, inventario, compras e informes con sus socios comerciales. Necesita un sistema para conectarse con sus proveedores y clientes a través de Internet que también se integran directamente con sus aplicaciones existentes de línea de negocio (LOB).  
  
 El vendedor es un proveedor de tamaño medio de circuitos integrados de alto rendimiento (ICs). Actualmente se comunican con sus socios comerciales mediante el teléfono, fax, correo electrónico con adjunta Microsoft [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] Web, FTP y hojas de cálculo de las aplicaciones. No realice EDI. Sus interacciones con todos los socios comerciales son diferentes, según las necesidades del cliente y sus propias tecnologías. Desea realizar sus procesos empresariales más eficaz para reducir los costos de transacción, mejorar la satisfacción del cliente y obtener una ventaja competitiva.  
  
## <a name="the-present-business-process"></a>El proceso empresarial está presente  
 Sin una solución integrada, el proceso de pedido de compra para el fabricante y el proveedor funciona del siguiente modo:  
  
1. Un cliente del fabricante del equipo de alta tecnología envía un pedido al fabricante a través de un sitio Web.  
  
2. En respuesta a la orden original, un empleado del fabricante crea una solicitud de pedido de compra en su aplicación ERP de LOB para el proveedor de IC.  
  
3. La solicitud de pedido de compra recorre las distintas partes de la empresa de fabricación que tienen para grabar, procesar, revisar y autorizar la solicitud de pedido de compra. Este procesamiento y enrutamiento son una combinación de los procesos automatizados para los usuarios del sistema ERP y procesos manuales, como el correo electrónico con un [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] hoja de cálculo.  
  
4. Un empleado crea una solicitud de pedido de compra en el correo electrónico y lo envía al proveedor. Un número de otros empleados comunicarse a través de EDI, fax o correo electrónico a otros proveedores Repita este proceso. Diferentes departamentos usan distintos procesos. Con esos proveedores que utilicen EDI, un empleado del fabricante debe crear sigue un mensaje de manualmente desde el sistema ERP.  
  
5. Un empleado en el proveedor recibe el mensaje y, a continuación, manualmente las claves en su sistema ERP, cambiar el formato de los datos. Por correo electrónico, el empleado notifica a otros empleados de la solicitud.  
  
6. Los demás empleados analizan la solicitud. Si es necesario, notifican a sus propios proveedores de piezas de la necesidad de partes. Según el proveedor, utilice fax, teléfono, correo electrónico o FTP para notificar a sus proveedores.  
  
7. Después de que concede con sus proveedores y los departamentos de TI, cada empleado acepta o rechaza cada elemento de línea de producto del pedido de compra y, a continuación, confirma o rechaza el pedido de compra e indica que está pendiente. Estas tareas realizan en el sistema ERP.  
  
8. Un empleado del proveedor crea una respuesta de pedido de compra en el correo electrónico, confirmar o rechazar cada elemento de línea de la solicitud, o crear un mensaje que indica el pedido está pendiente. El empleado del proveedor envía el mensaje de respuesta al fabricante. Si un elemento de línea está pendiente, más adelante creará otro mensaje que indica si se acepta o se rechaza el elemento pendiente.  
  
9. Un empleado del fabricante recibe la respuesta de pedido de compra. Vuelva a escribir el orden en su sistema ERP de back-end.  
  
10. Otro empleado analiza la confirmación de pedido de compra y, a continuación, crea una respuesta al cliente original, confirma el pedido. Envían esta respuesta a través de correo electrónico.  
  
## <a name="the-rosettanet-solution"></a>La solución de RosettaNet  
 Microsoft BizTalk Server y [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] automatizar y estandarizar el proceso de solicitud y respuesta de pedido de compra. Usar un sistema integrado, minimiza la cantidad de intervención manual, la cantidad de papel de control y el uso de máquinas de fax y teléfonos. Mayoría de los procesos es transacciones automatizadas entre los equipos de servidor integrado. Cuando los empleados deben realizar manualmente una operación, lo hacen normalmente en sistemas ERP de back-end. La siguiente ilustración muestra el sistema integrado.  
  
 ![&#60;Ningún cambio&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-integrated-supply-chain-scenario.gif "RN3_Integrated_Supply_Chain_Scenario")  
  
 En este escenario, un sistema integrado cambia los siguientes procesos:  
  
- Una conexión de RosettaNet Implementation Framework (RNIF) reemplaza las interacciones manuales rutinarias entre el fabricante y el proveedor de IC. El sistema automáticamente envía y recibe mensajes, enruta los datos a sistemas de back-end y reconoce y responde a los mensajes. El fabricante y el proveedor usa [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] para implementar la conexión RNIF.  
  
- Una conexión RNIF reemplaza la conexión de EDI entre el fabricante, el proveedor de IC y otros socios comerciales. Esto permite que los datos de ruta de sistema de integración automáticamente a los sistemas de back-end de los socios comerciales. Algunos de los socios comerciales asociados use [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] para implementar la conexión RNIF; otras usan una solución compatible con RosettaNet diferente.  
  
- Para aquellos partners más pequeños que no tienen una solución compatible con RosettaNet, el fabricante y el proveedor de IC crean servicios Web que pueden tener acceso los asociados con un explorador Web. El servicio Web utiliza una conexión RNIF estándar para comunicarse con el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema en el fabricante o el proveedor de IC.  
  
- Los mensajes intercambian entre los fabricantes y los proveedores siguen esquemas que cumplen con los procesos de interfaz de socio (PIP) de RosettaNet estándar. Estos esquemas reemplazar los formatos utilizados en EDI y FTP. Todos los socios comerciales usan los mismos esquemas; no debe asignar los datos entre los mensajes.  
  
- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] valida automáticamente todos los mensajes con los esquemas, reducir el riesgo de errores de datos.  
  
- Los administradores pueden intervenir en [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] servidores mediante las herramientas de software administrativo. Encargados de tomar decisiones empresariales en los equipos cliente pueden usar herramientas de supervisión de negocio hospedadas en aplicaciones basadas en Office de Microsoft o herramientas. Ambos son procesos eficientes que mantienen el sistema operativo de forma eficaz y proporcionar más visibilidad de cómo el sistema y cómo la empresa: se está ejecutando.  
  
### <a name="message-flow"></a>Flujo de mensajes  
 El proceso empresarial ahora incluye los siguientes pasos:  
  
1. Un cliente del fabricante del equipo de alta tecnología envía un pedido al fabricante a través de un sitio Web.  
  
2. En respuesta a la orden original, un empleado del fabricante genera una solicitud de pedido de compra en orden y el sistema de administración de inventario de la empresa. Esta aplicación de LOB es un sistema ERP con una interfaz de usuario basada en Web.  
  
3. El sistema envía a la solicitud de pedido de compra, aún en el formato nativo al sistema ERP, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].  
  
4. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] genera automáticamente un mensaje de solicitud de pedido de compra que cumplen el PIP de 3A4 definido por la organización RosettaNet. Esta solicitud de pedido de compra está en formato XML. El PIP define el contenido del mensaje.  
  
   > [!NOTE]
   >  El PIP 3A4 se asegura de que todas las solicitudes de pedido de compra y las respuestas son iguales en el formulario. Este PIP forma parte de una colección de PIP definido por RosettaNet que forman un completo sistema de mensajería interconectado. Por ejemplo, antes de enviar el mensaje de 3A4, puede buscar el comprador precio y disponibilidad (PIP 3A2), solicitar una oferta (PIP 3A1) o transferir su carro de la compra (3A3 PIP). Después de enviar la solicitud de pedido de compra, el comprador puede cambiar el orden de compra (3A8 PIP), cancelar el pedido de compra (3A9 PIP), consultar el estado de pedido de compra (3A5 PIP) o distribuir el estado del pedido de compra (3A6 PIP). La organización RosettaNet ha estandarizado todos estos mensajes.  
  
5. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] ajusta el mensaje de solicitud (denominado el contenido del servicio) con encabezados RNIF que permiten [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] transmitir el mensaje a través de Internet a otro [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] equipo en el sitio del proveedor. RNIF define cómo los asociados intercambian mensajes a través de Internet.  
  
6. El fabricante [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema envía la solicitud de pedido de compra al proveedor de IC [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema.  
  
7. El proveedor [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema N recibe la solicitud de pedido de compra. Si se tratara de una solicitud de acción única (uno sin una respuesta correspondiente), el proveedor [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema devolvería un mensaje de señal que confirma la recepción del mensaje. Sin embargo, dado que se trata de un mensaje de doble acción, el proveedor [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema devolverá un mensaje de señal de confirmación de recibo seguido de un mensaje de respuesta también.  
  
8. El proveedor [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema quita los encabezados RNIF del mensaje de solicitud de pedido de compra, procesa el contenido del mensaje del servicio y, a continuación, enruta la solicitud al sistema ERP del proveedor.  
  
9. Los empleados del proveedor trabajan en el sistema ERP para procesar el pedido. Si tienen que enviar mensajes a sus propios proveedores de piezas, lo hacen con la misma de BizTalk y [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema. El departamento de TI puede personalizar el sistema para responder automáticamente al fabricante.  
  
10. Un empleado del sistema ERP del proveedor se utiliza para generar un mensaje de respuesta de pedido de compra y, a continuación, enruta el mensaje de respuesta para el proveedor [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema.  
  
11. El proveedor [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema genera un mensaje de respuesta de pedido de compra PIP 3A4, ajusta el contenido del mensaje de respuesta del servicio en los encabezados RNIF y, a continuación, envía la respuesta de pedido de compra al fabricante [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema.  
  
12. El fabricante [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema recibe la respuesta de pedido de compra y, a continuación, envía un mensaje de confirmación de recepción para el proveedor [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]. El proveedor [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sistema enruta la confirmación al sistema ERP del proveedor.  
  
13. El fabricante [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] quita los encabezados RNIF del mensaje de respuesta, procesa el contenido del servicio y, a continuación, enruta la respuesta de pedido de compra para la aplicación de ERP del fabricante.  
  
14. Un empleado del fabricante analiza todos los mensajes de confirmación de pedido de compra y, a continuación, crea una respuesta al cliente original, confirma el pedido. El empleado, a continuación, envía esta respuesta a través de correo electrónico.  
  
## <a name="advantages-of-the-btarn-solution"></a>Ventajas de la solución BTARN  
 BizTalk Server y [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] automatizar la mayoría de los aspectos del proceso de solicitud y respuesta de pedido de compra. Lo hacen no solo para el fabricante y el proveedor de IC, sino también para todos los demás socios comerciales que han adoptado compatible con RosettaNet soluciones como parte de la administración de la cadena de suministro.  
  
 Un sistema de integración minimiza la cantidad de intervención manual y la cantidad de manejo de papel. Mayoría de los procesos implica interacciones automáticas entre los equipos de servidor integrado. El fabricante y el proveedor de IC tienen un alto grado de control sobre y la visibilidad sobre sus procesos. Automáticamente se recibir confirmaciones y puede mantener una prueba de rechazo.  
  
 El sistema automatizado mediante [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] permite que el fabricante y el proveedor hacer lo siguiente:  
  
-   Reducir los tiempos de ciclo de realización de pedidos  
  
-   Reducir incertidumbres en el proceso y aumentar la confiabilidad del proceso  
  
-   Disminuir los tiempos de entrega y los tiempos de respuesta de la oferta  
  
-   Reducir modificar manualmente información de tiempo invertido, obtención de información que falte o corrección de errores  
  
-   Proporcionar visibilidad y habilitar la supervisión del proceso y el seguimiento de mensajes  
  
## <a name="see-also"></a>Vea también  
 [Cómo resuelve BizTalk Server la necesidad empresarial](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [La necesidad de integración de socios comerciales](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md)   
 [El desafío de la cadena de suministro](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md)   
 [La solución de cadena de suministro](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md)   
 [Escenario de ejemplo basado en concentrador](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md)