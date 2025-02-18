package com.example.demo.pet;

import java.util.List;

import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.DeleteMapping;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.PutMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

import lombok.AllArgsConstructor;

@RestController
@RequestMapping("/pets")
@AllArgsConstructor
public class PetController {

    private PetService perservice;
    
    @GetMapping("/all")
    public ResponseEntity<List<Pet>> getPets() {
        return new ResponseEntity<>(perservice.getPets(), HttpStatus.OK);
    }
    
    @PostMapping("/add")
    public ResponseEntity<Pet> add(@RequestBody Pet pet) {
        return new ResponseEntity<>(perservice.add(pet), HttpStatus.CREATED);
    }
    
    @PutMapping("/update")
    public ResponseEntity<Pet> update(@RequestBody Pet pet) {
        return new ResponseEntity<>(perservice.update(pet), HttpStatus.CREATED);
    }
    
    @DeleteMapping("/{id}")
    public void delete(@PathVariable("id") Integer id) {
        perservice.delete(id);
    }
}
