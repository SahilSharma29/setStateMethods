# setStateMethods

Method 1

parent component
 const [state, setState] = useState({
    Wifi: false,
    BillsInclude: false,
    Parking: false,
    Kitchen: false,
    TV: false,
    WashingMachine: false,
    Garden: false,
  });
  
    const onChangeToggle = (checkBoxKey, value) => {
    setState({...state, [checkBoxKey]: value});
  };
  
     <AccomodationCheckbox
                      defaulValue={state}
                      ToggleCheckBox={onChangeToggle}
                    />
  
  when state value is manage on other component and set in parent component like this
  Child component
  {array.map(item => {
        return (
          <View>
            <View style={styles.checkBoxContainer}>
              <View style={[styles.checkBox]}>
                <CheckBox
                  // style={{backgroundColor: 'yellow',}}
                  // disabled={true}
                  value={defaulValue[item]}
                  onValueChange={newValue => ToggleCheckBox(item, newValue)}
                  tintColor={color.orange}
                  onCheckColor={color.white}
                  onFillColor={color.orange}
                  boxType="square"
                  lineWidth={2}
                />
              </View>
              <Text>{item}</Text>
            </View>
          </View>
        );
      })}
      
      
    Method 2
    When all statte in same component
      const [createDig, setcreateDig] = useState({
    refNumber: '',
    name: '',
    description: '',
    contactNumber: '',
  });
   setcreateDig(prev => ({...prev, refNumber: dig.reference_number}))
   
   method 3
  const [state, setState] = useState({
    locationName: '',
    addressLine1: '',
    addressLine2: '',
    postCode: '',
    county: '',
    loading: false,
    manualInsertCounty: true,
    disabled: true,
    latitude: '',
    longitude: '',
    city: '',
  });
  
 onChangeText={locationName => setState({...state, locationName})}
 onChangeText={postCode => setState({...state, postCode})}
 onChangeText={addressLine1 => setState({...state, addressLine1})}
