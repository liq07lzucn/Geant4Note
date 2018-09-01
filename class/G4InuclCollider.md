<!-- G4InuclCollider.md --- 
;; 
;; Description: 
;; Author: Hongyi Wu(吴鸿毅)
;; Email: wuhongyi@qq.com 
;; Created: 六 9月  1 11:23:08 2018 (+0800)
;; Last-Updated: 六 9月  1 11:29:40 2018 (+0800)
;;           By: Hongyi Wu(吴鸿毅)
;;     Update #: 3
;; URL: http://wuhongyi.cn -->

# G4InuclCollider

**public G4CascadeColliderBase**

**最核心部分！！！**

```cpp
  void collide(G4InuclParticle* bullet, G4InuclParticle* target, G4CollisionOutput& globalOutput);
  
G4ElementaryParticleCollider
G4IntraNucleiCascader
G4VCascadeDeexcitation
	G4PreCompoundDeexcitation
	G4CascadeDeexcitation
```

## class

```cpp
public:
  G4CascadeColliderBase(const G4String& name, G4int verbose=0);
  virtual ~G4CascadeColliderBase();

  // For use with top-level Propagate to preload a set of secondaries
  virtual void rescatter(G4InuclParticle* /*bullet*/,
			 G4KineticTrackVector* /*theSecondaries*/,
			 G4V3DNucleus* /*theNucleus*/,
			 G4CollisionOutput& /*globalOutput*/) { ; }

  virtual void setVerboseLevel(G4int verbose=0);

protected:
  G4InteractionCase interCase;		// Determine bullet vs. target

  // Decide whether to use G4ElementaryParticleCollider or not
  virtual G4bool useEPCollider(G4InuclParticle* bullet, 
			       G4InuclParticle* target) const;

  // Decide whether to use G4IntraNuclearCascader or not
  virtual G4bool inelasticInteractionPossible(G4InuclParticle* bullet,
					      G4InuclParticle* target, 
					      G4double ekin) const;

  // ==> Provide same interfaces as G4CascadeCheckBalance itself
  G4CascadeCheckBalance* balance;

  // Validate output for energy, momentum conservation, etc.
  virtual G4bool validateOutput(G4InuclParticle* bullet,
				G4InuclParticle* target,
				G4CollisionOutput& output);

  // This is for use after de-excitation
  virtual G4bool validateOutput(const G4Fragment& fragment,
				G4CollisionOutput& output);

  // This is for use with G4EPCollider
  virtual G4bool validateOutput(G4InuclParticle* bullet,
				G4InuclParticle* target,
		const std::vector<G4InuclElementaryParticle>& particles);

private:
  // Copying of modules is forbidden
  G4CascadeColliderBase(const G4CascadeColliderBase&);
  G4CascadeColliderBase& operator=(const G4CascadeColliderBase&);
```

<!-- G4InuclCollider.md ends here -->