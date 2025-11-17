# Lab 11
This is Group I (Luke and James)'s submission for Lab 11 - Bluetooth.

## Activity -- Add a Service

For this activity, we used 
`att_read_callback_handle_little_endian_16()`
instead of 
`att_read_callback_handle_blob()`
because it was easier to transmit 2 bytes instead of one.

Therefore, to have the correct value on our service, we had to do some bitmasking operations (shown below)
`uint16_t temp_data = (uint16_t)(temp * 100);`
`uint16_t bottom = (temp_data & 0x00FF) << 8;`
`uint16_t top = ((temp_data >> 8) & 0xFF);`
`temp_data = top | bottom;`

This will swap the top and bottom bytes of temp_data.

Thanks for reading!
