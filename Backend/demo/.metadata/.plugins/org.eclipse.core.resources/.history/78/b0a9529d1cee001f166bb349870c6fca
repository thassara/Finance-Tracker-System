package com.example.demo.pet;

import java.util.List;
import java.util.Optional;

import org.springframework.stereotype.Service;

import lombok.AllArgsConstructor;

@Service
@AllArgsConstructor
public class PetserviceImplement implements PetService {

    private PetRepository petrepo;

    @Override
    public Pet add(Pet pet) {
        return petrepo.save(pet);
    }

    @Override
    public List<Pet> getPets() {
        return petrepo.findAll();
    }

    @Override
    public Pet update(Pet pet) {
        if (petrepo.existsById(pet.getId())) {
            return petrepo.save(pet);
        } else {
            throw new RuntimeException("Pet not found for update");
        }
    }

    @Override
    public void delete(Integer id) {
        petrepo.deleteById(id);
    }

    @Override
    public Optional<Pet> getById(Integer id) throws Exception {
        return Optional.ofNullable(petrepo.findById(id)
            .orElseThrow(() -> new Exception("Pet not Found")));
    }
}
