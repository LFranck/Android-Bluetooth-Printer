# Android Bluetooth Printer
Android library for using thermal printers via bluetooth connection.

## Example usage
```
BluetoothAdapter btAdapter = BluetoothAdapter.getDefaultAdapter();
BluetoothDevice mBtDevice = btAdapter.getBondedDevices().iterator().next();   // Get first paired device

final BluetoothPrinter mPrinter = new BluetoothPrinter(mBtDevice);
mPrinter.connectPrinter(new BluetoothPrinter.PrinterConnectListener() {
  
  @Override
  public void onConnected() {
    mPrinter.setAlign(BluetoothPrinter.ALIGN_CENTER);
    mPrinter.printText("Hello World!");
    mPrinter.addNewLine();
    
    mPrinter.finish();
  }
  
  @Override
  public void onFailed() {
    Log.d("BluetoothPrinter", "Conection failed");
  }
  
});

```
Thanks to [imrankst1221](https://github.com/imrankst1221/Thermal-Printer-in-Android)
