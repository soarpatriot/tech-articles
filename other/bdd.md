
### BDD

BDD is a software engineering process based on TDD. BDD combines the best practices of TDD, domain-driven development (DDD), and object-oriented programming (OOP).


** Example **

```
  context "create statsion" do 
    it "success" do 
      stationable_id = 12
      stationable_type = "City"
      description = "aaa"
      address ="bb"      
      lan = 12.03      
      long = 12.05      
      points = [{lantitude:13.10,longitude: 45.31},{lantitude: 34.2,longitude: 23.3}]
      res = auth_json_post stations_path, description: description, address: address, lantitude: lan, longitude: long, points: points, stationable_id: stationable_id, stationable_type: stationable_type
      
      expect(res[:description]).to eq(description)
      expect(res[:lantitude]).to eq(lan)

    end
  end 

```

