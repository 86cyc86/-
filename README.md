# -
下拉菜单的二级联动
<th>
                                <select name="deviceArea" v-model="selected">
                                    <option value="">设备区域</option>
                                    <option value="{{area.id}}" v-for="area in areas">
                                        {{area.name}}
                                    </option>
                                </select>
                            </th>
                            <th>
                                <select name="deviceName">
                                    <option value="">设备</option>
                                    <option value="{{device.id}}" v-for="device in devices | filterBy device(selected)">
                                        {{device.name}}
                                    </option>
                                </select>
                            </th>
                            
                            
                           device:function (id) {
            return function(item){
                return item.areaid == id;}
        }
